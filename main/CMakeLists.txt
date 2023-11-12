set(SOURCES main.cpp ../mount_spiffs.c ../file_server.c)
idf_component_register(SRCS ${SOURCES}
                      INCLUDE_DIRS . ../include
                      EMBED_FILES "favicon.ico" "upload_script.html"
                      REQUIRES nvs_flash esp_timer driver spiffs vfs esp_event esp_https_server espWifi)
