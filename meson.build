project('uSocketsMeson', ['c', 'cpp'],
      version : '1.0',
      default_options : ['cpp_std=c++17', 'warning_level=3'])

zlib = dependency('zlib', required : true)
deps = [zlib]

if get_option('with_openssl')
   openssl = dependency('openssl', required : true)
   deps += openssl
   add_project_arguments('-DLIBUS_USE_OPENSSL', language : 'c')
endif

if get_option('with_wolfssl')
   wolfssl = dependency('wolfssl', required : true)
   deps += wolfssl
   add_project_arguments('-DLIBUS_USE_WOLFSSL', language : 'c')
endif

if get_option('with_libuv')
   libuv = dependency('libuv', required : true)
   deps += libuv
   add_project_arguments('-DLIBUS_USE_LIBUV', language : 'c')
endif

if get_option('with_gcd')
   libdispatch = dependency('libdispatch', required : true)
   deps += libdispatch
   add_project_arguments('-DLIBUS_USE_GCD', language : 'c')
endif

if get_option('with_asan')
   sanitizers = dependency('sanitizers', required : true)
   deps += sanitizers
   add_project_arguments('-fsanitize=address -g', language : 'c')
endif

includes = include_directories('./uSockets/src')

lib = static_library('uSocketsMeson',
       'uSockets/src/bsd.c',
       'uSockets/src/context.c',
       'uSockets/src/loop.c',
       'uSockets/src/socket.c',
       'uSockets/src/crypto/openssl.c',
       'uSockets/src/crypto/sni_tree.cpp',
       'uSockets/src/crypto/wolfssl.c',
       'uSockets/src/eventing/gcd.c',
       'uSockets/src/eventing/libuv.c',
       'uSockets/src/eventing/epoll_kqueue.c',
       install : true,
       dependencies : deps,
       include_directories : includes)


uSocketsMeson_dep = declare_dependency(link_with : lib,
      include_directories : includes, dependencies : deps)
