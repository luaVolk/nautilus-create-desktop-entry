project('nautilus-create-desktop-entry',
  version: '1.3',
  meson_version: '>= 0.40.0'
)

package = 'nautilus-create-desktop-entry'
destination = 'nautilus-python'
filename = 'nautilus-create-desktop-entry.py'

i18n = import('i18n')
pkgdata_dir = join_paths(get_option('prefix'), get_option('datadir'), meson.project_name())
extension_dir = join_paths(get_option('datadir'), destination, 'extensions')

subdir('data')
subdir('po')

install_subdir('src', install_dir: pkgdata_dir)

# Configuration params
conf = configuration_data()
conf.set('DATADIR', pkgdata_dir)
conf.set('PROJECT', meson.project_name())

configure_file(
  input : join_paths(package, filename + '.in'),
  output : filename,
  configuration : conf,
  install_dir: extension_dir
)

meson.add_install_script('meson_post_install.py')