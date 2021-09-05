Bevy Engine を使った Rust Game

reference: https://github.com/jeremychone-channel/rust-invaders

## Bevy

https://bevyengine.org

https://github.com/bevyengine/bevy

## Assets

- [Player, Laser, Enemy Sprites](https://opengameart.org/content/space-shooter-redux)
- [Explosion](https://opengameart.org/content/explosion)


## memo

MacBook Air (M1, 2020) で `cargo run` すると `shaderc-sys v0.7.3` で `couldn't find required command: "cmake"` エラーとなる


<details>
  <summary>error console</summary>
  
  ```console
    The following warnings were emitted during compilation:

    warning: shaderc: searching for native shaderc libraries on system;  use '--features build-from-source' to force building from source code
    warning: shaderc: cannot find native shaderc library on system; falling back to build from source

    error: failed to run custom build command for `shaderc-sys v0.7.3`

    Caused by:
    process didn't exit successfully: `/Users/ogawa/tmp/rust/rust-invaders/target/debug/build/shaderc-sys-1223ca869f5c437d/build-script-build` (exit status: 101)
    --- stdout
    cargo:warning=shaderc: searching for native shaderc libraries on system;  use '--features build-from-source' to force building from source code
    cargo:warning=shaderc: cannot find native shaderc library on system; falling back to build from source

    --- stderr
    thread 'main' panicked at '

    couldn't find required command: "cmake"

    ', /Users/ogawa/.cargo/registry/src/github.com-1ecc6299db9ec823/shaderc-sys-0.7.3/build/cmd_finder.rs:55:13
    note: run with `RUST_BACKTRACE=1` environment variable to display a backtrace
    warning: build failed, waiting for other jobs to finish...
    error: build failed}
  ```
</details>

issue  

https://github.com/bevyengine/bevy/issues/1360

https://github.com/bevyengine/bevy/issues/928#issuecomment-763000067




`cmake` を `brew install`

```sh
$ brew install cmake
$ file (which cmake)
/opt/homebrew/bin/cmake: Mach-O 64-bit executable arm64
$ cmake --version
cmake version 3.21.2

CMake suite maintained and supported by Kitware (kitware.com/cmake).
```

```sh
$ cargo clean
$ cargo run
   Compiling libc v0.2.101
   Compiling proc-macro2 v1.0.29
   Compiling unicode-xid v0.2.2
   Compiling cfg-if v1.0.0
   Compiling syn v1.0.65
   Compiling bitflags v1.2.1
   Compiling serde_derive v1.0.130
   Compiling serde v1.0.130
   Compiling lazy_static v1.4.0
   Compiling autocfg v1.0.1
   Compiling memchr v2.4.1
   Compiling version_check v0.9.3
   Compiling libm v0.2.1
   Compiling byteorder v1.4.3
   Compiling pin-project-lite v0.2.7
   Compiling once_cell v1.8.0
   Compiling log v0.4.14
   Compiling parking_lot_core v0.8.5
   Compiling scopeguard v1.1.0
   Compiling futures-core v0.3.17
   Compiling erased-serde v0.3.16
   Compiling cache-padded v1.1.1
   Compiling futures-io v0.3.17
   Compiling parking v2.0.0
   Compiling fastrand v1.5.0
   Compiling waker-fn v1.1.0
   Compiling regex-syntax v0.6.25
   Compiling ppv-lite86 v0.2.10
   Compiling downcast-rs v1.2.0
   Compiling event-listener v2.5.1
   Compiling slab v0.4.4
   Compiling async-task v4.0.3
   Compiling Inflector v0.11.4
   Compiling fixedbitset v0.4.0
   Compiling ryu v1.0.5
   Compiling serde_json v1.0.67
   Compiling itoa v0.4.8
   Compiling core-foundation-sys v0.8.2
   Compiling foreign-types-shared v0.1.1
   Compiling ansi_term v0.12.1
   Compiling crossbeam-utils v0.8.5
   Compiling glob v0.3.0
   Compiling same-file v1.0.6
   Compiling anyhow v1.0.43
   Compiling crc32fast v1.2.1
   Compiling adler32 v1.2.0
   Compiling base64 v0.13.0
   Compiling hashbrown v0.11.2
   Compiling fixedbitset v0.2.0
   Compiling bit-vec v0.6.3
   Compiling block v0.1.6
   Compiling bindgen v0.56.0
   Compiling glam v0.15.2
   Compiling lazycell v1.3.0
   Compiling bytemuck v1.7.2
   Compiling peeking_take_while v0.1.2
   Compiling rustc-hash v1.1.0
   Compiling color_quant v1.1.0
   Compiling scoped_threadpool v0.1.9
   Compiling shlex v0.1.1
   Compiling core-foundation-sys v0.7.0
   Compiling hex v0.4.3
   Compiling core-foundation-sys v0.6.2
   Compiling ahash v0.4.7
   Compiling io-kit-sys v0.1.0
   Compiling cfg_aliases v0.1.1
   Compiling ttf-parser v0.12.3
   Compiling cpal v0.13.4
   Compiling range-alloc v0.1.2
   Compiling ab_glyph_rasterizer v0.1.4
   Compiling arrayvec v0.5.2
   Compiling copyless v0.1.5
   Compiling cfg-if v0.1.10
   Compiling libm v0.1.4
   Compiling inflections v1.1.1
   Compiling svg_fmt v0.4.1
   Compiling dispatch v0.2.0
   Compiling rectangle-pack v0.3.0
   Compiling vec_map v0.8.2
   Compiling xi-unicode v0.3.0
   Compiling fnv v1.0.7
   Compiling instant v0.1.10
   Compiling libloading v0.7.0
   Compiling tracing-core v0.1.19
   Compiling sharded-slab v0.1.3
   Compiling num-traits v0.2.14
   Compiling num-integer v0.1.44
   Compiling indexmap v1.7.0
   Compiling num-rational v0.3.2
   Compiling num-iter v0.1.42
   Compiling thread_local v1.1.3
   Compiling lock_api v0.4.5
   Compiling fxhash v0.2.1
   Compiling concurrent-queue v1.2.2
   Compiling ahash v0.7.4
   Compiling nom v5.1.2
   Compiling foreign-types v0.3.2
   Compiling walkdir v2.3.2
   Compiling deflate v0.8.6
   Compiling miniz_oxide v0.3.7
   Compiling clang-sys v1.2.2
   Compiling bit-set v0.5.2
   Compiling hashbrown v0.9.1
   Compiling wgpu-core v0.7.1
   Compiling regex-automata v0.1.10
   Compiling hexasphere v3.4.0
   Compiling owned_ttf_parser v0.12.1
   Compiling storage-map v0.3.0
   Compiling matchers v0.0.1
   Compiling ab_glyph v0.2.11
   Compiling aho-corasick v0.7.18
   Compiling quote v1.0.9
   Compiling gpu-alloc-types v0.2.0
   Compiling gpu-descriptor-types v0.1.1
   Compiling wgpu-types v0.7.0
   Compiling tracing-log v0.1.2
   Compiling jobserver v0.1.24
   Compiling getrandom v0.2.3
   Compiling num_cpus v1.13.0
   Compiling filetime v0.2.15
   Compiling malloc_buf v0.0.6
   Compiling fsevent-sys v4.0.0
   Compiling raw-window-handle v0.3.3
   Compiling mach v0.3.2
   Compiling mach v0.2.3
   Compiling futures-lite v1.12.0
   Compiling async-channel v1.6.1
   Compiling core-foundation v0.9.1
   Compiling crossbeam-channel v0.5.1
   Compiling png v0.16.8
   Compiling core-foundation v0.7.0
   Compiling core-foundation v0.6.4
   Compiling rand_core v0.6.3
   Compiling cc v1.0.70
   Compiling stretch v0.3.2
   Compiling regex v1.5.4
   Compiling slice-deque v0.3.0
   Compiling petgraph v0.5.1
   Compiling core-graphics-types v0.1.1
   Compiling notify v5.0.0-pre.10
   Compiling core-graphics v0.19.2
   Compiling spirv_headers v1.5.0
   Compiling euclid v0.22.6
   Compiling approx v0.5.0
   Compiling async-executor v1.4.1
   Compiling rand_chacha v0.3.1
   Compiling cmake v0.1.45
   Compiling cexpr v0.4.0
   Compiling core-graphics v0.22.2
   Compiling objc_exception v0.1.2
   Compiling spirv-reflect v0.2.3
   Compiling spirv_cross v0.23.1
   Compiling minimp3-sys v0.3.2
   Compiling chrono v0.4.19
   Compiling glyph_brush_layout v0.2.3
   Compiling rand v0.8.4
   Compiling bevy_tasks v0.5.0
   Compiling guillotiere v0.6.2
   Compiling shaderc-sys v0.7.3
   Compiling image v0.23.14
   Compiling objc v0.2.7
   Compiling cocoa-foundation v0.1.0
   Compiling core-video-sys v0.1.4
   Compiling metal v0.21.0
   Compiling cocoa v0.24.0
   Compiling thiserror-impl v1.0.29
   Compiling tracing-attributes v0.1.15
   Compiling gltf-derive v0.15.2
   Compiling winit v0.24.0
   Compiling thiserror v1.0.29
   Compiling coreaudio-sys v0.2.8
   Compiling naga v0.3.2
   Compiling tracing v0.1.26
   Compiling gpu-alloc v0.3.0
   Compiling gpu-descriptor v0.1.1
   Compiling minimp3 v0.5.1
   Compiling gfx-hal v0.7.0
   Compiling smallvec v1.6.1
   Compiling toml v0.5.8
   Compiling uuid v0.8.2
   Compiling glam v0.13.1
   Compiling tracing-serde v0.1.2
   Compiling ron v0.6.4
   Compiling gfx-backend-empty v0.7.0
   Compiling bevy_utils v0.5.0
   Compiling gilrs-core v0.3.1
   Compiling find-crate v0.6.3
   Compiling tracing-subscriber v0.2.20
   Compiling gltf-json v0.15.2
   Compiling parking_lot v0.11.2
   Compiling gilrs v0.8.1
   Compiling bevy_reflect_derive v0.5.0
   Compiling bevy_ecs_macros v0.5.0
   Compiling bevy_derive v0.5.0
   Compiling gltf v0.15.2
   Compiling bevy_reflect v0.5.0
   Compiling coreaudio-rs v0.10.0
   Compiling bevy_ecs v0.5.0
   Compiling bevy_math v0.5.0
   Compiling rodio v0.13.1
   Compiling gfx-auxil v0.8.0
   Compiling gfx-backend-metal v0.7.0
   Compiling bevy_app v0.5.0
   Compiling bevy_log v0.5.0
   Compiling bevy_core v0.5.0
   Compiling bevy_transform v0.5.0
   Compiling bevy_window v0.5.0
   Compiling bevy_input v0.5.0
   Compiling bevy_dynamic_plugin v0.5.0
   Compiling bevy_diagnostic v0.5.0
   Compiling bevy_winit v0.5.0
   Compiling bevy_gilrs v0.5.0
   Compiling bevy_asset v0.5.1
   Compiling wgpu v0.7.1
   Compiling bevy_scene v0.5.0
   Compiling bevy_audio v0.5.0
   Compiling shaderc v0.7.3
   Compiling bevy_render v0.5.0
   Compiling bevy_sprite v0.5.0
   Compiling bevy_pbr v0.5.0
   Compiling bevy_wgpu v0.5.0
   Compiling bevy_gltf v0.5.0
   Compiling bevy_text v0.5.0
   Compiling bevy_ui v0.5.0
   Compiling bevy_internal v0.5.0
   Compiling bevy v0.5.0
   Compiling rust-invaders v0.1.0 (/Users/ogawa/tmp/rust/rust-invaders)
    Finished dev [unoptimized + debuginfo] target(s) in 2m 31s
     Running `target/debug/rust-invaders`
Hello, world!
```


