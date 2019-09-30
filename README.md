# mediasoup broadcaster demo (libmediasoupclient v3)

[libmediasoupclient][libmediasoupclient] based application that takes the system microphone and webcam and produces the media to the specified room in [mediasoup-demo][mediasoup-demo] application.


## Resources

* mediasoup website and documentation: [mediasoup.org](https://mediasoup.org)
* mediasoup support forum: [mediasoup.discourse.group](https://mediasoup.discourse.group)


## Usage

Once installed (see **Installation** below):

```bash
SERVER_URL=https://my.mediasoup-demo.org:4443 ROOM_ID=broadcaster build/broadcaster
```

Environment variables:

* `SERVER_URL`: The URL of the mediasoup-demo HTTP API server (required).
* `ROOM_ID`: Room id (required).
* `WEBRTC_DEBUG`: Enable libwebrtc full logging if "true" (optional).

## Dependencies

* [libmediasoupclient][libmediasoupclient] (already included in the repository)
* [cpr][cpr] (already included in the repository)
* OpenSSL (must be installed in the system including its headers)


## Installation

```bash
git clone https://github.com/versatica/mediasoup-broadcaster-demo.git

cmake . -Bbuild                                              \
  -DLIBWEBRTC_INCLUDE_PATH:PATH=${PATH_TO_LIBWEBRTC_SOURCES} \
  -DLIBWEBRTC_BINARY_PATH:PATH=${PATH_TO_LIBWEBRTC_BINARY}   \
  -DOPENSSL_INCLUDE_DIR:PATH=${PATH_TO_OPENSSL_HEADERS}      \
  -DCMAKE_USE_OPENSSL=ON

make -C build
```

*NOTE:* `PATH_TO_OPENSSL_HEADERS` is `/usr/local/opt/openssl/include` if you install OpenSSL using Homebrew in OSX.




[mediasoup-demo]: https://github.com/versatica/libmediasoupclient
[libmediasoupclient]: https://github.com/versatica/libmediasoupclient
[cpr]: https://github.com/whoshuu/cpr
