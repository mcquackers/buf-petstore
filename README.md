# buf-petstore
A repository containing example of a potential bug I found with buf

I encountered an issue when using buf Workspaces in tandem with remote dependencies.
I found that when using a subdirectory/submodule whose path includes a path already in the workspace, remote dependencies seem to break.
Individual steps going from successful generation with no-workspace/remote-deps to workspace/failing-remote-deps are listed in the commit messages

Example:
```
buf-petstore
|--buf.yaml
|--buf.lock
|--buf.work.yaml
|__townville
|  |__petstore
|    |__v1
|      |__petstore.proto
|__submodule
|  |__townville
|    |__currency
|      |__v1
|        |__currency.proto
```
