Open that keepassxc folder in Codex and give it this prompt:

Build and launch this KeePassXC feature branch for manual testing on Windows.

Read the repository's contributor guidance and INSTALL.md. Inspect the
installed tools and set up a native Windows build using MSVC, CMake,
and vcpkg. Use the dependency versions and options in this checkout;
it uses Qt 6.

Build the GUI and relevant tests. Run the Auto-Type and configuration
suites and the focused GUI settings tests. Deploy the required Qt
runtime files so the executable can launch.

Launch the built application with separate test settings. Tell me
the executable path and any validation limitations.

The feature adds “Minimize when performing entry-level AutoType”,
enabled by default. Disabling it must keep KeePassXC open while
automatically switching to the previously focused application and typing.

Do not push. Keep any necessary source fixes minimal and commit them
separately with brief messages.

KeePassXC recommends Visual Studio’s C++ build environment and vcpkg for Windows. The initial dependency build can take substantial time. Windows build setup (https://github.com/keepassxreboot/keepassxc/wiki/Set-up-Build-Environment-on-Windows)

For manual testing, create an entry with dummy credentials and use Notepad as the destination:

- Checked: Auto-Type reaches Notepad and KeePassXC minimizes or hides.
- Unchecked: Auto-Type reaches Notepad automatically while KeePassXC stays open.
- Repeat using the context menu, toolbar, and Ctrl+Shift+V, including username/password variants.
- Check maximized-window behavior and that the setting survives restarting KeePassXC.
