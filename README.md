# onnxruntime_vendor
vendor package for [onnxruntime](https://onnxruntime.ai/)

## Usage

```
# package.xml
<depend>onnxruntime_vendor<depend>

# CMakeLists.txt
find_package(onnxruntime_vendor REQUIRED)
find_package(onnxruntime REQUIRED)

target_link_libraries(your_target
  onnxruntime::onnxruntime
)
```

