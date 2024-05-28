project('sdldemo', 'c', default_options: 'default_library=static')

sdl2_dep = dependency('sdl2')

executable(
  'sdlprog',
  'sdlprog.c',
  dependencies: sdl2_dep,
  install: true,
  install_dir: '/tmp/sdlprog',
)
