project('uSocketsMeson', ['c', 'cpp'],
      version : '1.0',
      default_options : ['cpp_std=c++17', 'warning_level=3'])

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
       include_directories : include_directories('uSockets/src'))
