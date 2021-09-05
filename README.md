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
<summary>error</summary>
```
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
error: build failed
```
</details>

issue  

https://github.com/bevyengine/bevy/issues/1360

https://github.com/bevyengine/bevy/issues/928#issuecomment-763000067

