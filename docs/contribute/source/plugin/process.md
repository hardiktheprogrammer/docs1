---
sidebar_position: 3
---

# Build WasmEdge With WasmEdge-Process Plug-in

## Prerequisites

The prerequisites of the WasmEdge-Process plug-in is the same as the [WasmEdge building environment on the Linux platforms](../os/linux.md).

## Build WasmEdge with WasmEdge-Process Plug-in

To enable the WasmEdge WasmEdge-Process, developers need to [building the WasmEdge from source](../build_from_src.md) with the cmake option `-DWASMEDGE_PLUGIN_PROCESS=On`.

```bash
cd <path/to/your/wasmedge/source/folder>
cmake -GNinja -Bbuild -DCMAKE_BUILD_TYPE=Release -DWASMEDGE_PLUGIN_PROCESS=On
cmake --build build
# For the WasmEdge-Process plugin, you should install this project.
cmake --install build
```

<!-- prettier-ignore -->
:::note
If the built `wasmedge` CLI tool cannot find the WasmEdge-Process plug-in, you can set the `WASMEDGE_PLUGIN_PATH` environment variable to the plug-in installation path (such as `/usr/local/lib/wasmedge/`, or the built plug-in path `build/plugins/wasmedge_process/`) to try to fix this issue.
:::

Then you will have an executable `wasmedge` runtime under `/usr/local/bin` and the WasmEdge-Process plug-in under `/usr/local/lib/wasmedge/libwasmedgePluginWasmEdgeProcess.so` after installation.
