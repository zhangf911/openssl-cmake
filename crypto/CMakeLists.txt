
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

include_directories(asn1)
include_directories(evp)
include_directories(modes)

#add_definitions(-DOPENSSL_SYS_WIN32)

file(GLOB SRCS o_dir.c crypto/o_str.c crypto/o_time.c crypto/mem.c crypto/mem_dbg.c
	asn1/*.c
	bio/*.c
	bn/*.c
	buffer/*.c
	dh/*.c
	evp/*.c
	err/*.c
	md5/*.c
	modes/*.c
	objects/*.c
	pem/*.c
	pkcs7/pk7_asn1.c pkcs7/pk7_lib.c pkcs7/pkcs7err.c pkcs7/pk7_doit.c pkcs7/pk7_smime.c pkcs7/pk7_attr.c pkcs7/pk7_mime.c pkcs7/bio_pk7.c
	pkcs12/*.c
	rand/*.c
	rsa/*.c
	seed/*.c
	sha/*.c
	stack/*.c
	x509/*.c
	x509v3/*.c)

add_library(crypto STATIC ${SRCS})
