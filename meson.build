project('uSocketsMeson', ['c', 'cpp'],
      version : '1.0',
      default_options : ['cpp_std=c++17', 'warning_level=3'])

zlib = dependency('zlib', required : true)
openssl = dependency('openssl', required : true)

deps = [zlib, openssl]

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
