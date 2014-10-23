#!/usr/bin/env python

Import('env_android')
Import('env_linux')
Import('env')
Import('sslpath')

print "Building openssl"

def runNdkBuild(env, target, source):
	import subprocess
	app = "ndk-build"
	print "Directory: %s"%sslpath
	subprocess.call([app,"-C", sslpath])

sslbuild    = Command("libs/armeabi/libssl.so", "", runNdkBuild)
cryptobuild = Command("libs/armeabi/libcrypto.so", "", runNdkBuild)
Depends(sslbuild, cryptobuild)
Default(sslbuild)
Return('sslbuild', 'cryptobuild')
