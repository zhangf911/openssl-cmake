
include_directories(${CMAKE_CURRENT_SOURCE_DIR})

include_directories(asn1)
include_directories(evp)
include_directories(modes)

add_definitions(-DOPENSSL_NO_ASM -DOPENSSL_NO_ENGINE)
add_definitions(
	-DOPENSSL_NO_RC1
	-DOPENSSL_NO_RC2
	-DOPENSSL_NO_RC3
	-DOPENSSL_NO_RC4
	-DOPENSSL_NO_RC5
	-DOPENSSL_NO_MD1
	-DOPENSSL_NO_MD2
	-DOPENSSL_NO_MD3
	-DOPENSSL_NO_MD4
	-DOPENSSL_NO_MDC2
	-DOPENSSL_NO_WHIRLPOOL
	-DOPENSSL_NO_RIPEMD
	-DOPENSSL_NO_CMS
	-DOPENSSL_NO_OCSP)

file(GLOB SRCS
	aes/*.c
	asn1/*.c
	bf/*.c
	bio/*.c
	bn/*.c
	buffer/*.c
	camellia/*.c
	cast/*.c
	cmac/*.c
	conf/*.c
	dh/*.c

	des/cbc_cksm.c des/cbc_enc.c  des/cfb64enc.c des/cfb_enc.c
	des/ecb3_enc.c des/ecb_enc.c  des/enc_read.c des/enc_writ.c
	des/fcrypt.c des/ofb64enc.c des/ofb_enc.c  des/pcbc_enc.c
	des/qud_cksm.c des/rand_key.c des/rpc_enc.c  des/set_key.c
	des/des_enc.c des/fcrypt_b.c
	des/xcbc_enc.c
	des/str2key.c  des/cfb64ede.c des/ofb64ede.c des/ede_cbcm_enc.c des/des_old.c des/des_old2.c
	des/read2pwd.c

	dsa/*.c
	dso/*.c
	ec/*.c
	ecdsa/*.c
	ecdh/*.c
	evp/

	evp/encode.c evp/digest.c evp/evp_enc.c evp/evp_key.c evp/evp_acnf.c evp/evp_cnf.c
	evp/e_des.c evp/e_bf.c evp/e_idea.c evp/e_des3.c evp/e_camellia.c
	evp/e_rc4.c evp/e_aes.c evp/names.c evp/e_seed.c
	evp/e_xcbc_d.c evp/e_rc2.c evp/e_cast.c evp/m_null.c evp/m_md5.c evp/m_sha.c evp/m_sha1.c m_wp.c
	evp/m_dss.c evp/m_dss1.c evp/m_mdc2.c evp/m_ripemd.c evp/m_ecdsa.c
	evp/p_open.c evp/p_seal.c evp/p_sign.c evp/p_verify.c evp/p_lib.c evp/p_enc.c evp/p_dec.c
	evp/bio_md.c evp/bio_b64.c evp/bio_enc.c evp/evp_err.c evp/e_null.c
	evp/c_all.c evp/c_allc.c evp/c_alld.c evp/evp_lib.c evp/bio_ok.c
	evp/evp_pkey.c evp/evp_pbe.c evp/p5_crpt.c evp/p5_crpt2.c
	evp/e_old.c evp/pmeth_lib.c evp/pmeth_fn.c evp/pmeth_gn.c evp/m_sigver.c evp/evp_fips.c
	evp/e_aes_cbc_hmac_sha1.c evp/e_rc4_hmac_md5.c

	err/*.c
	hmac/*.c

	idea/*.c
	lhash/*.c
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
	ui/*.c
	x509/*.c
	x509v3/*.c
	o_init.c o_dir.c o_str.c o_time.c ex_data.c cpt_err.c cryptlib.c mem.c mem_dbg.c mem_clr.c  cversion.c)

add_library(crypto STATIC ${SRCS})
