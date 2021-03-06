project('hexabomb-visu', 'cpp',
    default_options: ['cpp_std=c++17'],
    meson_version: '>=0.44.0',
    version: '0.1.0'
)

netorcai_client_cpp_dep = dependency('netorcai-client-cpp', required: true)
sfml_graphics_dep = dependency('sfml-graphics', required: true)
boost_dep = dependency('boost',
    modules: ['filesystem', 'system', 'program_options'], required: true)
threads_dep = dependency('threads', required: true)

src = [
    'src/main.cpp',
    'src/hexabomb-parse.cpp',
    'src/hexabomb-parse.hpp',
    'src/renderer.cpp',
    'src/renderer.hpp',
    'src/threads.cpp',
    'src/threads.hpp',
    'src/util.cpp',
    'src/util.hpp'
]

visu = executable('hexabomb-visu', src,
    dependencies: [netorcai_client_cpp_dep, sfml_graphics_dep, boost_dep, threads_dep],
    install: true, install_dir: 'bin'
)

share_files = [
    'assets/img/bomb.png',
    'assets/img/char.png',
    'assets/img/char_dead.png',
    'assets/img/char_special.png',
    'assets/img/explosion.png',
    'assets/fonts/DejaVuSansMono.ttf'
]

install_data(share_files, install_dir : 'share/hexabomb-visu')
