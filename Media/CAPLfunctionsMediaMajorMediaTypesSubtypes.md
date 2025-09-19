[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/CAPLfunctionsMediaMajorMediaTypesSubtypes.md)

**CAPL Functions** » **Media API** » **Major Media Types / Subtypes**

# Major Media Types / Subtypes

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

## Major Media Types

In a media type, the major type describes the overall category of the data, such as audio or video. The subtype, if present, further refines the major type. For example, if the major type is video, the subtype might be 32-bit RGB video. Subtypes also distinguish encoded formats, such as H.264 video, from uncompressed formats.

Major type and subtype are identified by strings and stored in the following properties:

- **[MajorType](Properties/CAPLfunctionMajorType.md)**: Major type
- **[Subtype](Properties/CAPLfunctionSubType.md)**: Subtype

You can use the following major types:

- **MediaType_Audio**: Audio
  - [Audio Subtypes](#AudioSubtypes)
- **MediaType_Stream**: Multiplexed stream or elementary stream
  - [Stream Subtypes](#StreamSubtypes)
- **MediaType_Timestamp**: Stream delivering timestamp values
  - [Timestamp Subtypes](#TimestampSubtypes)
- **MediaType_Video**: Video
  - [Video Subtypes](#VideoSubtypes)

## Audio Subtypes

The following audio subtype strings are defined. To specify the subtype, set the Subtype property on the media type.

When these subtypes are used, set the **MajorType** property to **MediaType_Audio**.

- **AudioFormat_AAC**: Advanced Audio Coding (AAC). The stream can contain raw AAC data or AAC data in an Audio Data Transport Stream (ADTS) stream. Format Tag: 0x1610
- **AudioFormat_ADTS**: Not used. Format Tag: 0x1600
- **AudioFormat_ALAC**: Apple Lossless Audio Codec. Supported in Windows 10 and later. Format Tag: 0x6C61
- **AudioFormat_AMR_NB**: Adaptative Multi-Rate audio. Supported in Windows 8.1 and later. Format Tag: 0x0057
- **AudioFormat_AMR_WB**: Adaptative Multi-Rate Wideband audio. Supported in Windows 8.1 and later. Format Tag: 0x0058
- **AudioFormat_AMR_WP**: Supported in Windows 8.1 and later. Format Tag: 0x7363
- **AudioFormat_Dolby_AC3**: Dolby Digital (AC-3). Format Tag: None
- **AudioFormat_Dolby_AC3_SPDIF**: Dolby AC-3 audio over Sony/Philips Digital Interface (S/PDIF). Format Tag: 0x0092
- **AudioFormat_Dolby_DDPlus**: Dolby Digital Plus. Format Tag: None
- **AudioFormat_DRM**: Encrypted audio data used with secure audio path. Format Tag: 0x0009
- **AudioFormat_DTS**: Digital Theater Systems (DTS) audio. Format Tag: 0x0008
- **AudioFormat_FLAC**: Free Lossless Audio Codec. Supported in Windows 10 and later. Format Tag: 0xF1AC
- **AudioFormat_Float**: Uncompressed IEEE floating-point audio. Format Tag: 0x0003
- **AudioFormat_MP3**: MPEG Audio Layer-3 (MP3). Format Tag: 0x0055
- **AudioFormat_MPEG**: MPEG-1 audio payload. Format Tag: 0x0050
- **AudioFormat_MSP**: Windows Media Audio 9 Voice codec. Format Tag: 0x000A
- **AudioFormat_Opus**: Opus. Supported in Windows 10 and later. Format Tag: 0x704F
- **AudioFormat_PCM**: Uncompressed PCM audio. Format Tag: 1
- **AudioFormat_QCELP**: QCELP (Qualcomm Code Excited Linear Prediction) audio. Format Tag: None
- **AudioFormat_WMASPDIF**: Windows Media Audio 9 Professional codec over S/PDIF. Format Tag: 0x0164
- **AudioFormat_WMAudio_Lossless**: Windows Media Audio 9 Lossless codec or Windows Media Audio 9.1 codec. Format Tag: 0x0163
- **AudioFormat_WMAudioV8**: Windows Media Audio 8 codec, Windows Media Audio 9 codec, or Windows Media Audio 9.1 codec. Format Tag: 0x0161
- **AudioFormat_WMAudioV9**: Windows Media Audio 9 Professional codec or Windows Media Audio 9.1 Professional codec. Format Tag: 0x0162

## Stream Subtypes

The following stream subtype strings are defined. To specify the subtype, set the Subtype property on the media type.

When these subtypes are used, set the **MajorType** property to **MediaType_Stream**.

- **StreamFormat_MPEG2Transport**: MPEG-2 transport stream.
- **StreamFormat_MPEG2Program**: MPEG-2 program stream.

**Notes**

Reading samples from an MPEG2-transport/program stream is not (yet) possible by use of a [Media Source Reader](CAPLfunctionsMediaSouceReader.md) created by [MediaCreateSourceReaderFromUrl](Functions/CAPLfunctionMediaCreateSourceReaderFromURL.md) since Windows does not provide an appropriate Media Source.

For obtaining samples from a file containing MPEG2-transport/program stream data you can use the [File Functions](../Other/CAPLfunctionsFileFunctions.md) in CAPL.

## Timestamp Subtypes

The following timestamp subtype strings are defined. To specify the subtype, set the Sub-type property on the media type.

When these subtypes are used, set the **MajorType** property to **MediaType_Timestamp**.

- **TimestampFormat_PTP**: PTP timestamp stream. Resolution: 64 Bit / 1 ns. Epoch: Unix (Midnight, 1 January 1970). Time Base: International Atomic Time (TAI).

## Video Subtypes

The following video subtype strings are defined. To specify the subtype, set the Subtype property on the media type.

When these subtypes are used, set the **MajorType** property to **MediaType_Video**.

### Uncompressed RGB Format

- **VideoFormat_RGB8**: RGB, 8 bits per pixel (bpp).
- **VideoFormat_RGB555**: RGB 555, 16 bpp.
- **VideoFormat_RGB565**: RGB 565, 16 bpp.
- **VideoFormat_RGB24**: RGB, 24 bpp.
- **VideoFormat_RGB32**: RGB, 32 bpp.
- **VideoFormat_ARGB32**: RGB, 32 bpp with alpha channel.

### YUV Formats: 8-Bit and Palettized

- **VideoFormat_AI44**: AI44, 4:4:4, Packed, Palettized.
- **VideoFormat_AYUV**: AYUV, 4:4:4, Packed, 8.
- **VideoFormat_I420**: I420, 4:2:0, Planar, 8.
- **VideoFormat_IYUV**: IYUV, 4:2:0, Planar, 8.
- **VideoFormat_NV11**: NV11, 4:1:1, Planar, 8.
- **VideoFormat_NV12**: NV12, 4:2:0, Planar, 8.
- **VideoFormat_UYVY**: UYVY, 4:2:2, Packed, 8.
- **VideoFormat_Y41P**: Y41P, 4:1:1, Packed, 8.
- **VideoFormat_Y41T**: Y41T, 4:1:1, Packed, 8.
- **VideoFormat_Y42T**: Y42T, 4:2:2, Packed, 8.
- **VideoFormat_YUY2**: YUY2, 4:2:2, Packed, 8.
- **VideoFormat_YVU9**: YVU9, 8:4:4, Planar, 9.
- **VideoFormat_YV12**: YV12, 4:2:0, Planar, 8.
- **VideoFormat_YVYU**: YVYU, 4:2:2, Packed, 8.

### YUV Formats: 10-Bit and 16-Bit

- **VideoFormat_P010**: P010, 4:2:0, Planar, 10.
- **VideoFormat_P016**: P016, 4:2:0, Planar, 16.
- **VideoFormat_P210**: P210, 4:2:2, Planar, 10.
- **VideoFormat_P216**: P216, 4:2:2, Planar, 16.
- **VideoFormat_v210**: v210, 4:2:2, Packed, 10.
- **VideoFormat_v216**: v216, 4:2:2, Packed, 16.
- **VideoFormat_v40**: v40, 4:4:4, Packed, 10.
- **VideoFormat_Y210**: Y210, 4:2:2, Packed, 10.
- **VideoFormat_Y216**: Y216, 4:2:2, Packed, 16.
- **VideoFormat_Y40**: Y40, 4:4:4, Packed, 10.
- **VideoFormat_Y416**: Y416, 4:4:4, Packed, 16.

### Luminance and Depth Formats

- **VideoFormat_L8**: 8-bit luminance only.
- **VideoFormat_L16**: 16-bit luminance only.
- **VideoFormat_D16**: 16-bit z-buffer depth.

### Encoded Video Types

- **VideoFormat_DV25**: DVCPRO 25 (525-60 or 625-50). Format Tag: 'dv25'
- **VideoFormat_DV50**: DVCPRO 50 (525-60 or 625-50). Format Tag: 'dv50'
- **VideoFormat_DVC**: DVC/DV Video. Format Tag: 'dvc '
- **VideoFormat_DVH1**: DVCPRO 100 (1080/60i, 1080/50i, or 720/60P). Format Tag: 'dvh1'
- **VideoFormat_DVHD**: HD-DVCR (1125-60 or 1250-50). Format Tag: 'dvhd'
- **VideoFormat_DVSD**: SDL-DVCR (525-60 or 625-50). Format Tag: 'dvsd'
- **VideoFormat_DVSL**: SD-DVCR (525-60 or 625-50). Format Tag: 'dvsl'
- **VideoFormat_H263**: H.263 video. Format Tag: 'H263'
- **VideoFormat_H264**: H.264-Video. Media samples contain H.264 bitstream data with start codes and has interleaved SPS/PPS. Each sample contains one complete picture, either one field or one frame. Format Tag: 'H264'
- **VideoFormat_H265**: H.265 video. Format Tag: 'H265'
- **VideoFormat_H264_ES**: H.264 elementary stream. This media type is the same as MFVideoFormat_H264, except media samples contain a fragmented H.264 bitstream. Each sample may contain a partial picture; multiple complete pictures; or one or more complete pictures plus a partial picture. Format Tag: Not applicable
- **VideoFormat_HEVC**: The HEVC Main profile and Main Still Picture profile. Each sample contains one complete picture. Supported in Windows 8.1 and later. Format Tag: 'HEVC'
- **VideoFormat_HEVC_ES**: This media type is the same as MFVideoFormat_HEVC, except media samples contain a fragmented HEVC bitstream. Each sample may contain a partial picture; multiple complete pictures; or one or more complete pictures plus a partial picture. Supported in Windows 8.1 and later. Format Tag: 'HEVS'
- **VideoFormat_M4S2**: MPEG-4 part 2 video. Format Tag: 'M4S2'
- **VideoFormat_MJPG**: Motion JPEG. Format Tag: 'MJPG'
- **VideoFormat_MP43**: Microsoft MPEG 4 codec version 3. This codec is no longer supported. Format Tag: 'MP43'
- **VideoFormat_MP4S**: ISO MPEG 4 codec version 1. Format Tag: 'MP4S'
- **VideoFormat_MP4V**: MPEG-4 part 2 video. Format Tag: 'MP4V'
- **VideoFormat_MPEG2**: MPEG-2 video. Format Tag: Not applicable
- **VideoFormat_VP80**: VP8 video. Format Tag: 'MPG1'
- **VideoFormat_VP90**: VP9 video. Format Tag: 'MPG1'
- **VideoFormat_MPG1**: MPEG-1 video. Format Tag: 'MPG1'
- **VideoFormat_MSS1**: Windows Media Screen codec version 1. Format Tag: 'MSS1'
- **VideoFormat_MSS2**: Windows Media Video 9 Screen codec. Format Tag: 'MSS2'
- **VideoFormat_WMV1**: Windows Media Video codec version 7. Format Tag: 'WMV1'
- **VideoFormat_WMV2**: Windows Media Video 8 codec. Format Tag: 'WMV2'
- **VideoFormat_WMV3**: Windows Media Video 9 codec. Format Tag: 'WMV3'
- **VideoFormat_WVC1**: SMPTE 421M ("VC-1"). Format Tag: 'WVC1'
- **VideoFormat_420O**: 8-bit per channel planar YUV 4:2:0 video. Format Tag: '420O'

[Media CAPL Functions](CAPLfunctionsMediaOverview.md)

© Vector Informatik GmbH

CANoe (Desktop Editions & Test Bench Editions) Version 18 SP3

[Contact/Copyright/License](../../Shared/ContactCopyrightLicense.md) | [Data Privacy Notice](https://www.vector.com/int/en/company/get-info/privacy-policy/)
