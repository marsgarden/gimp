if platform_windows

plugin_name = 'twain'

plugin_sources = [
  'tw_func.c',
  'tw_util.c',
  'tw_win.c',
  'twain.c',
]

plugin_sources += windows.compile_resources(
  gimp_plugins_rc,
  args: [
    '--define', 'ORIGINALFILENAME_STR="@0@"'.format(plugin_name+'.exe'),
    '--define', 'INTERNALNAME_STR="@0@"'    .format(plugin_name),
    '--define', 'TOP_SRCDIR="@0@"'          .format(meson.source_root()),
  ],
  include_directories: [
    rootInclude, appInclude,
  ],
)

twain = executable(plugin_name,
  plugin_sources,
  include_directories: [ rootInclude, ],
  dependencies: [
    glib, gtk3, gegl,
  ],
  link_with: [
    libgimp,
    libgimpcolor,
    libgimpbase,
  ],
  install: true,
  install_dir: gimpplugindir / 'plug-ins' / plugin_name,
)

endif