# buf-petstore
A repository containing example of a potential bug I found with buf

I encountered an issue when using buf Workspaces in tandem with remote dependencies.
I found that when using a subdirectory/submodule whose path includes a path already in the workspace, remote dependencies seem to break.
Individual steps going from successful generation with no-workspace/remote-deps to workspace/failing-remote-deps are listed in the commit messages

Example:
buf-petstore
|--buf.yaml
|--buf.lock
|--buf.work.yaml
|\_\_townville
|  |\_\_petstore
|    |\_\_v1
|      |\_\_petstore.proto
|\_\_submodule
|  |\_\_townville
|    |\_\_currency
|      |\_\_v1
|        |\_\_currency.proto
