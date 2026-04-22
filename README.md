## cyanrip-static

Docker image with [cyanrip](https://github.com/cyanreg/cyanrip), [ffmpeg](https://ffmpeg.org/ffmpeg.html) and [ffprobe](https://ffmpeg.org/ffprobe.html) built as static binaries with no external dependencies that can be used with any base image.

See [Dockerfile](Dockerfile) for versions used. In general, main **should** have the latest stable version of cyanrip, along with the compatible version of ffmpeg (~v7) and the below libraries. 
Versions can be kept up to date automatically using [bump](https://github.com/wader/bump).

### Usage

Build the image yourself:
```sh
docker build -t cyanrip-static .
```

Copy binary to local machine:
```sh
docker run -i --rm -u $UID:$GROUPS -v "$PWD:$PWD" -w "$PWD" cyanrip-static bash -c "cp /usr/local/bin/cyanrip ."
```

### Libraries

- [fontconfig](https://www.freedesktop.org/wiki/Software/fontconfig/)
- gray (full grayscale support)
- iconv (from musl)
- [lcms2](https://www.littlecms.com/)
- [libaom](https://aomedia.googlesource.com/aom/)
- [libaribb24](https://github.com/nkoriyama/aribb24)
- [libass](https://github.com/libass/libass)
- [libbluray](https://www.videolan.org/developers/libbluray.html)
- [libdav1d](https://code.videolan.org/videolan/dav1d)
- [libdavs2](https://github.com/pkuvcl/davs2)
- [libfdk-aac](https://github.com/mstorsjo/fdk-aac)
- [libfreetype](https://freetype.org/)
- [libfribidi](https://github.com/fribidi/fribidi)
- [libgme](https://github.com/mcfiredrill/libgme)
- [libgsm](https://github.com/timothytylee/libgsm)
- [libharfbuzz](https://github.com/harfbuzz/harfbuzz)
- [libjxl](https://github.com/libjxl/libjxl)
- [libkvazaar](https://github.com/ultravideo/kvazaar)
- [libmodplug](https://github.com/Konstanty/libmodplug)
- [libmp3lame](https://lame.sourceforge.io/)
- [libmysofa](https://github.com/hoene/libmysofa)
- [libopencore](https://sourceforge.net/projects/opencore-amr/)
- [libopenjpeg](https://www.openjpeg.org)
- [libopus](https://opus-codec.org)
- [librabbitmq](https://github.com/alanxz/rabbitmq-c)
- [librav1e](https://github.com/xiph/rav1e)
- [librsvg](https://gitlab.gnome.org/GNOME/librsvg)
- [librtmp](https://rtmpdump.mplayerhq.hu/)
- [librubberband](https://breakfastquay.com/rubberband/)
- [libshine](https://github.com/toots/shine)
- [libsnappy](https://google.github.io/snappy/)
- [libsoxr](https://sourceforge.net/projects/soxr/)
- [libspeex](https://github.com/xiph/speex)
- [libsrt](https://github.com/Haivision/srt)
- [libssh](https://gitlab.com/libssh/libssh-mirror)
- [libsvtav1](https://gitlab.com/AOMediaCodec/SVT-AV1)
- [libtheora](https://github.com/xiph/theora)
- [libtwolame](https://github.com/njh/twolame)
- [libuavs3d](https://github.com/uavs3/uavs3d)
- [libva](https://github.com/intel/libva)
- [libvidstab](https://github.com/georgmartius/vid.stab)
- [libvmaf](https://github.com/Netflix/vmaf)
- [libvo-amrwbenc](https://github.com/mstorsjo/vo-amrwbenc)
- [libvorbis](https://github.com/xiph/vorbis)
- [libvpl](https://github.com/intel/libvpl)
- [libvpx](https://github.com/webmproject/libvpx)
- [libvvenc](https://github.com/fraunhoferhhi/vvenc)
- [libwebp](https://chromium.googlesource.com/webm/libwebp)
- [libx264](https://www.videolan.org/developers/x264.html)
- [libx265](https://www.videolan.org/developers/x265.html) (multilib with support for 10 and 12 bits)
- [libxavs2](https://github.com/pkuvcl/xavs2)
- [libxevd](https://github.com/mpeg5/xevd)
- [libxeve](https://github.com/mpeg5/xeve)
- [libxml2](https://gitlab.gnome.org/GNOME/libxml2)
- [libxvid](https://labs.xvid.com)
- [libzimg](https://github.com/sekrit-twc/zimg)
- [libzmq](https://github.com/zeromq/libzmq)
- [openssl](https://openssl.org)
- [libcdio](https://github.com/libcdio/libcdio)
- [libcdio-paranoia](https://github.com/libcdio/libcdio-paranoia)
- [neon](https://notroj.github.io/neon/)
- [libmusicbrainz5](https://github.com/metabrainz/libmusicbrainz/)
- and all native ffmpeg codecs, formats, filters etc.

### Files in the image

- `/usr/local/bin/cyanrip`
- `/usr/local/bin/ffmpeg` ffmpeg binary
- `/usr/local/bin/ffprobe` ffprobe binary
- `/versions.json` JSON file with build versions of ffmpeg and libraries.

### Tags

TBC

### Security

Binaries are built with some hardening features but it's *still a good idea to run them as non-root even when used inside a container*, especially so if running on input files that you don't control.

### Thanks

- [@wader](https://github.com/wader) for doing the vast majority of the work!

### Contribute

Feel free to create issues or PRs if you have any improvements or encounter any problems. Please also consider making a [donation to the FFmpeg project](https://ffmpeg.org/donations.html) or to other projects used by this image if you find it useful.

Please also be mindful of the license limitations used by libraries this project uses and your own usage and potential distribution of such.
