# Project name and programming language
project('com.github.willjacksonuk.hello-grid', ['c', 'vala'])

# Include the translation module
i18n = import('i18n')

# Set our translation domain
add_global_arguments('-DGETTEXT_PACKAGE="@&@"'.format (meson.project_name()), language:'c')

# Create a new executable, list the files we want to compile, list the dependencies we need, and install
executable(
    meson.project_name(),
    'src/Application.vala',
    dependencies: [
        dependency('gtk+-3.0')
    ],
    install: true
)

# Translate and install our .desktop file
i18n.merge_file(
    input: join_paths('data', 'hello-grid.desktop.in'),
    output: meson.project_name() + '.dkestop',
    po_dir: join_paths(meson.source_root(), 'po'),
    type: 'desktop',
    install: true,
    install_dir: join_paths(get_option('datadir'), 'applications')
)

# Translate and install our .appdata file
i18n.merge_file(
    input: join_paths('data', 'hello-grid.appdata.xml.in'),
    output: meson.project_name() + '.appdata.xml',
    po_dir: join_paths(meson.source_root(), 'po'),
    install: true,
    install_dir: join_paths(get_option('datadir'), 'metainfo')
)

subdir('po')
