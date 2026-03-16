# origin-pack: STMicroelectronics::mbedtls@2.0.0
# file-format: 1.0.0
project(STMicroelectronics_mbedtls_2_0_0)
cmake_minimum_required(VERSION 3.20)
add_library(STMicroelectronics_mbedtls_2_0_0 INTERFACE)

# List of all CMSIS properties that influence conditions for this package
if(NOT DEFINED CMSIS_Dname)
  set(CMSIS_Dname "CMSIS_Dname not set")
  message(DEBUG "CMSIS_Dname is not set to any value")
endif()

if(NOT DEFINED CMSIS_Dvendor)
  set(CMSIS_Dvendor "CMSIS_Dvendor not set")
  message(DEBUG "CMSIS_Dvendor is not set to any value")
endif()


# Device specific defined symbols








# Enable all components in this package
if(CMSIS_ENTIRE_STMicroelectronics_mbedtls_2_0_0)
  list(APPEND CMSIS_COMPONENTS_LIST "Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:PSA API#Cversion:3.6.5")
  list(APPEND CMSIS_COMPONENTS_LIST "Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:MBED API#Cversion:3.6.5")
  list(APPEND CMSIS_COMPONENTS_LIST "Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:Core#Cversion:3.6.5")
  list(APPEND CMSIS_COMPONENTS_LIST "Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:SW Crypto#Cversion:3.6.5")
  list(APPEND CMSIS_COMPONENTS_LIST "Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:Persistent Storage#Cversion:3.6.5")
  list(APPEND CMSIS_COMPONENTS_LIST "Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:Secure Element#Cversion:3.6.5")
endif()

# All conditions used by this package

# condition: STMicroelectronics.mbedtls.2.0.0
# description: 
if((CMSIS_Dname MATCHES "STM32.*" AND CMSIS_Dvendor STREQUAL "STMicroelectronics:13"))
  set(STMicroelectronics.mbedtls.2.0.0 "1")
  message(DEBUG "CMSIS condition STMicroelectronics.mbedtls.2.0.0 enabled")
else()
  set(STMicroelectronics.mbedtls.2.0.0 0)
endif()


# condition: STMicroelectronics.mbedtls.2.0.0:MBED interface conditions
# description: Ensure Mbed TLS are satisfied
set(STMicroelectronics.mbedtls.2.0.0_MBED_interface_conditions "$<AND:$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:Core(#.*|$)>,>>,$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:SW Crypto(#.*|$)>,>>>")
message(DEBUG "CMSIS condition STMicroelectronics.mbedtls.2.0.0_MBED_interface_conditions enabled")


# condition: STMicroelectronics.mbedtls.2.0.0:PSA interface conditions
# description: Ensure PSA APIs are satisfied
set(STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions "$<AND:$<OR:$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:MBED API(#.*|$)>,>>,$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:Persistent Storage(#.*|$)>,>>,$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:Secure Element(#.*|$)>,>>>,$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:SW Crypto(#.*|$)>,>>>")
message(DEBUG "CMSIS condition STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions enabled")


# condition: STMicroelectronics.mbedtls.2.0.0:Persistent Storage conditions
# description: Ensure Mbed TLS APIs are selected before
set(STMicroelectronics.mbedtls.2.0.0_Persistent_Storage_conditions "$<AND:$<OR:$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:Core(#.*|$)>,>>,$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:Persistent Storage API(#.*|$)>,>>>,$<NOT:$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:MBED API(#.*|$)>,>>>>")
message(DEBUG "CMSIS condition STMicroelectronics.mbedtls.2.0.0_Persistent_Storage_conditions enabled")


# condition: STMicroelectronics.mbedtls.2.0.0:ST Secure Element conditions
# description: Ensure Mbed TLS APIs are selected before
set(STMicroelectronics.mbedtls.2.0.0_ST_Secure_Element_conditions "$<AND:$<OR:$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:Core(#.*|$)>,>>,$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:Persistent Storage(#.*|$)>,>>,$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:ST Crypto Driver API(#.*|$)>,>>>,$<NOT:$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:MBED API(#.*|$)>,>>>>")
message(DEBUG "CMSIS condition STMicroelectronics.mbedtls.2.0.0_ST_Secure_Element_conditions enabled")


# condition: STMicroelectronics.mbedtls.2.0.0:SW Crypto conditions
# description: Ensure Mbed TLS APIs are selected before
set(STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions "$<NOT:$<STREQUAL:$<FILTER:${CMSIS_COMPONENTS_LIST},INCLUDE,.*Cclass:Security#.*Cgroup:MbedTLS#.*Csub:Core(#.*|$)>,>>")
message(DEBUG "CMSIS condition STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions enabled")

# Files and components in this package
if("Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:PSA API#Cversion:3.6.5" IN_LIST CMSIS_COMPONENTS_LIST)  # PSA crypto interface
  message(DEBUG "Using component Security_MbedTLS_PSA_API_3_6_5")
  target_compile_definitions(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:-DCMSIS_USE_Security_MbedTLS_PSA_API_3_6_5=1>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/include/psa>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/include/psa/>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_aead.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_cipher.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_client.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_driver_wrappers_no_static.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_ecp.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_hash.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_mac.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_pake.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_rsa.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_slot_management.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_its_file.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_PSA_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_util.c>")
endif()

if("Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:MBED API#Cversion:3.6.5" IN_LIST CMSIS_COMPONENTS_LIST)  # Legacy crypto interface
  message(DEBUG "Using component Security_MbedTLS_MBED_API_3_6_5")
  target_compile_definitions(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_MBED_interface_conditions}:-DCMSIS_USE_Security_MbedTLS_MBED_API_3_6_5=1>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_MBED_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/configs/>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_MBED_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/include/mbedtls>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_MBED_interface_conditions}:${CMAKE_CURRENT_LIST_DIR}/include/mbedtls/>")
endif()

if("Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:Core#Cversion:3.6.5" IN_LIST CMSIS_COMPONENTS_LIST)  # Mbed TLS core implementations
  message(DEBUG "Using component Security_MbedTLS_Core_3_6_5")
  target_compile_definitions(STMicroelectronics_mbedtls_2_0_0 INTERFACE "-DCMSIS_USE_Security_MbedTLS_Core_3_6_5=1")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/include/")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/asn1parse.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/asn1write.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/base64.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/bignum.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/bignum_core.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/cipher.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/cipher_wrap.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/constant_time.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ctr_drbg.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/debug.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/entropy.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/entropy_poll.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/error.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/hkdf.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/hmac_drbg.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/md.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/memory_buffer_alloc.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/oid.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/pem.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/pk.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/pk_ecc.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/pk_wrap.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/pkcs12.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/pkcs5.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/pkparse.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/pkwrite.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/platform.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/platform_util.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_ffdh.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/rsa_alt_helpers.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_cache.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_ciphersuites.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_client.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_cookie.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_debug_helpers_generated.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_msg.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_ticket.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_tls.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_tls12_client.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_tls12_server.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_tls13_client.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_tls13_generic.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_tls13_keys.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/ssl_tls13_server.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/threading.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/timing.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/version.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/version_features.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/x509.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/x509_create.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/x509_crl.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/x509_crt.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/x509_csr.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/x509write.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/x509write_crt.c")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "${CMAKE_CURRENT_LIST_DIR}/library/x509write_csr.c")
endif()

if("Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:SW Crypto#Cversion:3.6.5" IN_LIST CMSIS_COMPONENTS_LIST)  # Mbed TLS SW crypto implementations
  message(DEBUG "Using component Security_MbedTLS_SW_Crypto_3_6_5")
  target_compile_definitions(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:-DCMSIS_USE_Security_MbedTLS_SW_Crypto_3_6_5=1>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/include/>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/aes.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/aria.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/camellia.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/ccm.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/chacha20.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/chachapoly.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/cmac.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/des.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/dhm.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/ecdh.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/ecdsa.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/ecjpake.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/ecp.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/ecp_curves.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/gcm.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/md5.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/nist_kw.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/poly1305.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/ripemd160.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/rsa.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/sha1.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/sha256.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/sha3.c>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_SW_Crypto_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/sha512.c>")
endif()

if("Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:Persistent Storage#Cversion:3.6.5" IN_LIST CMSIS_COMPONENTS_LIST)  # Storage
  message(DEBUG "Using component Security_MbedTLS_Persistent_Storage_3_6_5")
  target_compile_definitions(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_Persistent_Storage_conditions}:-DCMSIS_USE_Security_MbedTLS_Persistent_Storage_3_6_5=1>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_Persistent_Storage_conditions}:${CMAKE_CURRENT_LIST_DIR}/include/>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_Persistent_Storage_conditions}:${CMAKE_CURRENT_LIST_DIR}/library>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_Persistent_Storage_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_storage.c>")
endif()

if("Cvendor:STMicroelectronics#Cclass:Security#Cgroup:MbedTLS#Csub:Secure Element#Cversion:3.6.5" IN_LIST CMSIS_COMPONENTS_LIST)  # Secure Element
  message(DEBUG "Using component Security_MbedTLS_Secure_Element_3_6_5")
  target_compile_definitions(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_ST_Secure_Element_conditions}:-DCMSIS_USE_Security_MbedTLS_Secure_Element_3_6_5=1>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_ST_Secure_Element_conditions}:${CMAKE_CURRENT_LIST_DIR}/include/>")
  target_include_directories(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_ST_Secure_Element_conditions}:${CMAKE_CURRENT_LIST_DIR}/library>")
  target_sources(STMicroelectronics_mbedtls_2_0_0 INTERFACE "$<${STMicroelectronics.mbedtls.2.0.0_ST_Secure_Element_conditions}:${CMAKE_CURRENT_LIST_DIR}/library/psa_crypto_se.c>")
endif()

