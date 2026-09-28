# lichtfeld-portable-build (temporary)

Throwaway CI repo. The only content that matters is
`.github/workflows/build-portable.yml`, which builds
[LichtFeld Studio](https://github.com/MrNeRF/LichtFeld-Studio) in
`BUILD_PORTABLE=ON` mode on a GitHub-hosted `windows-2022` runner (which has
its own admin rights, unlike the laptop this was set up from) and uploads
the resulting `dist/` folder as a workflow artifact.

This exists only because the laptop that needs the binary has no local admin
rights, so Visual Studio Build Tools + the CUDA Toolkit can't be installed
there directly. The portable build only needs an NVIDIA driver to run, which
that laptop already has. See `lichtfeld-noadmin-build-plan.txt` in the main
project for full context. This is a temporary fix for the splat pipeline,
not the long-term build path.

No scene/capture data is or should ever be involved here -- this only
compiles LichtFeld's own public open-source code.
