cmake_minimum_required(VERSION 3.2)
project(openwebrtc_0_3_0)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(GLIB_INCLUDE_PATH  "/home/david74/cerbero/dist/linux_x86_64/include/glib-2.0")
set(GLIB_CONFIG_INCLUDE_PATH  "/home/david74/cerbero/dist/linux_x86_64/lib/glib-2.0/include")
set(LIBNICE_CONFIG_INCLUDE_PATH  "/home/david74/cerbero/dist/linux_x86_64/include/nice")
set(GST_INCLUDE_PATH  "/home/david74/cerbero/dist/linux_x86_64/include/gstreamer-1.0")
set(GST_CONFIG_INCLUDE_PATH  "/home/david74/cerbero/dist/linux_x86_64/lib/gstreamer-1.0/include")
set(OWR_INCLUDE_PATH
    "./bridge/client" "./bridge/seed" "./bridge/shared" "./bridge/worker" "./bridge/"
    "./gst/" "./local/" "./owr/" "./transport/" "./"
)

include_directories(
    ${GLIB_INCLUDE_PATH} ${GLIB_CONFIG_INCLUDE_PATH} ${GST_INCLUDE_PATH} ${GST_CONFIG_INCLUDE_PATH}
    ${LIBNICE_CONFIG_INCLUDE_PATH} ${OWR_INCLUDE_PATH}
)

set(SOURCE_FILES
    bindings/java/owr_bridge_jni.c
    bridge/client/domutils.js.h
    bridge/client/sdp.js.h
    bridge/client/webrtc.js.h
    bridge/seed/websocket.js.h
    bridge/seed/workerinit.js.h
    bridge/seed/workerutils.js.h
    bridge/shared/wbjsonrpc.js.h
    bridge/worker/bridgeserver.js.h
    bridge/worker/peerhandler.js.h
    bridge/daemon.c
    bridge/owr_bridge.c
    bridge/owr_bridge.h
    gst/owr_gst_audio_renderer.c
    gst/owr_gst_audio_renderer.h
    gst/owr_gst_media_source.c
    gst/owr_gst_media_source.h
    gst/owr_gst_video_renderer.c
    gst/owr_gst_video_renderer.h
    local/owr_audio_renderer.c
    local/owr_audio_renderer.h
    local/owr_device_list.c
    local/owr_device_list_avf_private.h
    local/owr_device_list_private.h
    local/owr_image_renderer.c
    local/owr_image_renderer.h
    local/owr_image_renderer_private.h
    local/owr_image_server.c
    local/owr_image_server.h
    local/owr_local.c
    local/owr_local.h
    local/owr_local_media_source.c
    local/owr_local_media_source.h
    local/owr_local_media_source_private.h
    local/owr_media_renderer.c
    local/owr_media_renderer.h
    local/owr_media_renderer_private.h
    local/owr_video_renderer.c
    local/owr_video_renderer.h
    local/owr_video_renderer_private.h
    local/owr_window_registry.c
    local/owr_window_registry.h
    local/owr_window_registry_private.h
    owr/owr.c
    owr/owr.h
    owr/owr_media_source.c
    owr/owr_media_source.h
    owr/owr_media_source_private.h
    owr/owr_private.h
    owr/owr_types.c
    owr/owr_types.h
    owr/owr_utils.c
    owr/owr_utils.h
    tests/list_devices.c
    tests/test_client.c
    tests/test_data_channel.c
    tests/test_gst_io.c
    tests/test_init.c
    tests/test_self_view.c
    tests/test_send_receive.c
    tests/test_utils.c
    tests/test_utils.h
    transport/owr_audio_payload.c
    transport/owr_audio_payload.h
    transport/owr_candidate.c
    transport/owr_candidate.h
    transport/owr_candidate_private.h
    transport/owr_data_channel.c
    transport/owr_data_channel.h
    transport/owr_data_channel_private.h
    transport/owr_data_channel_protocol.h
    transport/owr_data_session.c
    transport/owr_data_session.h
    transport/owr_data_session_private.h
    transport/owr_media_session.c
    transport/owr_media_session.h
    transport/owr_media_session_private.h
    transport/owr_payload.c
    transport/owr_payload.h
    transport/owr_payload_private.h
    transport/owr_remote_media_source.c
    transport/owr_remote_media_source.h
    transport/owr_remote_media_source_private.h
    transport/owr_session.c
    transport/owr_session.h
    transport/owr_session_private.h
    transport/owr_transport_agent.c
    transport/owr_transport_agent.h
    transport/owr_video_payload.c
    transport/owr_video_payload.h
    config.h)

add_executable(openwebrtc_0_3_0 ${SOURCE_FILES})