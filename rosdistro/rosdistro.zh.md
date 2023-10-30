在 rosdep 使用流程中，我们会有如下两个步骤

<tmpl z-lang="bash">
{{sudo}}rosdep init
rosdep update
</tmpl>

我们替换为以下步骤

首先手动模拟 rosdep init，这可以参考 [GitHub RAW 镜像](../github-raw/) 中 rosdep init 一节。

之后执行以下指令。

<tmpl z-lang="bash">
# 为 rosdep update 换源
export ROSDISTRO_INDEX_URL={{endpoint}}/index-v4.yaml
rosdep update

# 每次 rosdep update 之前，均需要增加该环境变量
# 为了持久化该设定，可以将其写入 .bashrc 中，例如
echo 'export ROSDISTRO_INDEX_URL={{endpoint}}/index-v4.yaml' >> ~/.bashrc
</tmpl>
