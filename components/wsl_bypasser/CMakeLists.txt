idf_component_register(
    SRCS "wsl_bypasser.c"
    INCLUDE_DIRS "interface"
    REQUIRES esp_wifi)

# --wrap redirects all calls to ieee80211_raw_frame_sanity_check inside
# libnet80211.a to our __wrap_ implementation in wsl_bypasser.c.
# Works on ESP32, ESP32-S2, and ESP32-S3.
# @see https://forum.arduino.cc/t/an-arbitrary-raw-wifi-frame-transmission-on-esp32-s2-s3/1437789
target_link_libraries(${COMPONENT_LIB} -Wl,--wrap=ieee80211_raw_frame_sanity_check)
