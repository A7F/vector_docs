[Open topic with navigation](../../../../CANoeDEFamily.htm#Topics/CAPLFunctions/Media/CAPLfunctionsMediaProperties.md)

[CAPL Functions](../CAPLfunctions.md) » [Media API](CAPLfunctionsMediaOverview.md) » Media Properties

# Media Properties

[Valid for](../../Shared/FeatureAvailability.md): CANoe DE • CANoe4SW DE

The following properties apply to media types.

## General Format Properties

These properties can be applied to all media types.

- **AllSamplesIndependent**: [AllSamplesIndependent](Properties/CAPLfunctionAllSamplesIndependent.md) - dword  
  Specifies whether each sample is independent of the other samples in the stream.

- **Compressed**: [Compressed](Properties/CAPLfunctionCompressed.md) - dword  
  Specifies whether the media data is compressed.

- **FixedSizeSamples**: [FixedSizeSamples](Properties/CAPLfunctionFixedSizeSamples.md) - dword  
  Specifies whether the samples have a fixed size.

- **MajorType**: [MajorType](Properties/CAPLfunctionMajorType.md) - string  
  [Major type](CAPLfunctionsMediaMajorMediaTypesSubtypes.md)

- **SampleSize**: [SampleSize](Properties/CAPLfunctionSampleSize.md) - dword  
  Size of each sample, in bytes.

- **Subtype**: [Subtype](Properties/CAPLfunctionSubType.md) - string  
  [Subtype](CAPLfunctionsMediaMajorMediaTypesSubtypes.md)

## Audio Format Properties

These properties can be applied to media types whose major type equals **MediaType_Audio**.

- **AacAudioProfileLevelIndication**: [AacAudioProfileLevelIndication](Properties/CAPLfunctionAacAudioProfileLevelIndication.md) - dword  
  Specifies the audio profile and level of an Advanced Audio Coding (AAC) stream.

- **AacPayloadType**: [AacPayloadType](Properties/CAPLfunctionAacPayloadType.md) - dword  
  Specifies the payload type for an Advanced Audio Coding (AAC) stream.

- **AudioAvgBytesPerSecond**: [AudioAvgBytesPerSecond](Properties/CAPLfunctionAudioAvgBytesPerSecond.md) - dword  
  Average number of bytes per second.

- **AudioBitsPerSample**: [AudioBitsPerSample](Properties/CAPLfunctionAudioBitsPerSample.md) - dword  
  Number of bits per audio sample.

- **AudioBlockAlignment**: [AudioBlockAlignment](Properties/CAPLfunctionAudioBlockAlignment.md) - dword  
  Block alignment, in bytes.

- **AudioChannelMask**: [AudioChannelMask](Properties/CAPLfunctionAudioChannelMask.md) - dword  
  Specifies the assignment of audio channels to speaker positions.

- **AudioFloatSamplesPerSecond**: [AudioFloatSamplesPerSecond](Properties/CAPLfunctionAudioFloatSamplesPerSecond.md) - double  
  Number of audio samples per second (floating-point value).

- **AudioFolddownMatrix**: [AudioFolddownMatrix](Properties/CAPLfunctionAudioFolddownMatrix.md) - byte[]  
  Specifies how an audio decoder should transform multichannel audio to stereo output.

- **AudioNumChannels**: [AudioNumChannels](Properties/CAPLfunctionAudioNumChannels.md) - dword  
  Number of audio channels.

- **AudioSamplesPerBlock**: [AudioSamplesPerBlock](Properties/CAPLfunctionAudioSamplesPerBlock.md) - dword  
  Number of audio samples contained in one compressed block of audio data.

- **AudioSamplesPerSecond**: [AudioSamplesPerSecond](Properties/CAPLfunctionAudioSamplesPerSecond.md) - dword  
  Number of audio samples per second (integer value).

- **AudioValidBitsPerSample**: [AudioValidBitsPerSample](Properties/CAPLfunctionAudioValidBitsPerSample.md) - dword  
  Number of valid bits of audio data in each audio sample.

- **AudioWmadrcAvgref**: [AudioWmadrcAvgref](Properties/CAPLfunctionAudioWmadrcAvgref.md) - dword  
  Reference average volume level of a Windows Media Audio file.

- **AudioWmadrcAvgtarget**: [AudioWmadrcAvgtarget](Properties/CAPLfunctionAudioWmadrcAvgtarget.md) - dword  
  Target average volume level of a Windows Media Audio file.

- **AudioWmadrcPeakref**: [AudioWmadrcPeakref](Properties/CAPLfunctionAudioWmadrcPeakref.md) - dword  
  Reference peak volume level of a Windows Media Audio file.

- **AudioWmadrcPeaktarget**: [AudioWmadrcPeaktarget](Properties/CAPLfunctionAudioWmadrcPeaktarget.md) - dword  
  Target peak volume level of a Windows Media Audio file.

- **OriginalWaveFormatTag**: [OriginalWaveFormatTag](Properties/CAPLfunctionOriginalWaveFormatTag.md) - dword  
  Contains the original WAVE format tag for an audio stream.

## Video Format Properties

These properties can be applied to media types whose major type equals **MediaType_Video**.

- **AvgBitErrorRate**: [AvgBitErrorRate](Properties/CAPLfunctionAvgBitErrorRate.md) - dword  
  Data error rate.

- **AvgBitrate**: [AvgBitrate](Properties/CAPLfunctionAvgBitrate.md) - dword  
  Approximate data rate of the video stream.

- **DefaultStride**: [DefaultStride](Properties/CAPLfunctionDefaultStride.md) - dword  
  Default surface stride.

- **DrmFlags**: [DrmFlags](Properties/CAPLfunctionDrmFlags.md) - dword  
  Specifies whether the video requires enforcing copy protection.

- **FrameRate**: [FrameRate](Properties/CAPLfunctionFrameRate.md) - qword  
  Frame rate.

- **FrameRateRangeMax**: [FrameRateRangeMax](Properties/CAPLfunctionFrameRateRangeMax.md) - qword  
  The maximum frame rate supported by a video capture device.

- **FrameRateRangeMin**: [FrameRateRangeMin](Properties/CAPLfunctionFrameRateRangeMin.md) - qword  
  The minimum frame rate supported by a video capture device.

- **FrameSize**: [FrameSize](Properties/CAPLfunctionFrameSize.md) - qword  
  Width and height of the video frame.

- **GeometricAperture**: [GeometricAperture](Properties/CAPLfunctionGeometricAperture.md) - dword  
  Geometric aperture.

- **InterlaceMode**: [InterlaceMode](Properties/CAPLfunctionInterlaceMode.md) - dword  
  Describes how the frames are interlaced.

- **MaxKeyframeSpacing**: [MaxKeyframeSpacing](Properties/CAPLfunctionMaxKeyframeSpacing.md) - dword  
  Maximum number of frames from one key frame to the next.

- **MinimumDisplayAperture**: [MinimumDisplayAperture](Properties/CAPLfunctionMinimumDisplayAperture.md) - byte[]  
  Minimum display aperture.

- **MpegSequenceHeader**: [MpegSequenceHeader](Properties/CAPLfunctionMpegSequenceHeader.md) - byte[]  
  MPEG-1 or MPEG-2 sequence header.

- **MpegStartTimeCode**: [MpegStartTimeCode](Properties/CAPLfunctionMpegStartTimeCode.md) - dword  
  Group-of-pictures (GOP) start time code.

- **Mpeg2Flags**: [Mpeg2Flags](Properties/CAPLfunctionMpeg2Flags.md) - dword  
  Miscellaneous flags for MPEG-2 video.

- **Mpeg2Level**: [Mpeg2Level](Properties/CAPLfunctionMpeg2Level.md) - dword  
  MPEG-2 or H.264 level.

- **Mpeg2Profile**: [Mpeg2Profile](Properties/CAPLfunctionMpeg2Profile.md) - dword  
  MPEG-2 or H.264 profile.

- **Original4cc**: [Original4cc](Properties/CAPLfunctionOriginal4cc.md) - dword  
  Contains the original codec FOURCC for a video stream.

- **PadControlFlags**: [PadControlFlags](Properties/CAPLfunctionPadControlFlags.md) - dword  
  Aspect ratio of the output rectangle.

- **Palette**: [Palette](Properties/CAPLfunctionPalette.md) - dword  
  Palette entries.

- **PanScanAperture**: [PanScanAperture](Properties/CAPLfunctionPanScanAperture.md) - dword  
  Defines the 4×3 region of video that should be displayed in pan/scan mode.

- **PanScanEnabled**: [PanScanEnabled](Properties/CAPLfunctionPanScanEnabled.md) - dword  
  Specifies whether pan/scan mode is enabled.

- **PixelAspectRatio**: [PixelAspectRatio](Properties/CAPLfunctionPixelAspectRatio.md) - qword  
  Pixel aspect ratio.

- **SourceContentHint**: [SourceContentHint](Properties/CAPLfunctionSourceContentHint.md) - dword  
  Intended aspect ratio.

- **TransferFunction**: [TransferFunction](Properties/CAPLfunctionTransferFunction.md) - dword  
  Conversion function from RGB to R'G'B'.

- **Video3d**: [Video3d](Properties/CAPLfunctionVideo3d.md) - dword  
  Specifies whether a video stream contains 3D content.

- **VideoChromaSiting**: [VideoChromaSiting](Properties/CAPLfunctionVideoChromaSiting.md) - dword  
  Describes how chroma was sampled for Y'Cb'Cr' video.

- **VideoLighting**: [VideoLighting](Properties/CAPLfunctionVideoLighting.md) - dword  
  Optimal lighting conditions for viewing.

- **VideoNominalRange**: [VideoNominalRange](Properties/CAPLfunctionVideoNominalRange.md) - dword  
  Nominal range of the color information.

- **VideoPrimaries**: [VideoPrimaries](Properties/CAPLfunctionVideoPrimaries.md) - dword  
  Color primaries.

- **VideoRotation**: [VideoRotation](Properties/CAPLfunctionVideoRotation.md) - dword  
  Specifies the rotation of a video frame in the counter-clockwise direction.

- **YuvMatrix**: [YuvMatrix](Properties/CAPLfunctionYuvMatrix.md) - dword  
  Conversion matrix from the Y'Cb'Cr' color space to the R'G'B' color space.

## Other Format Properties

The following properties apply to interleaved DV video.

- **DvAauxSrcPack0**: [DvAauxSrcPack0](Properties/CAPLfunctionDvAauxSrcPack0.md) - dword  
  Audio auxiliary (AAUX) source control pack for the first audio block.

- **DvAauxCtrlPack0**: [DvAauxCtrlPack0](Properties/CAPLfunctionDvAauxCtrlPack0.md) - dword  
  AAUX source control pack for the second audio block.

- **DvAauxSrcPack1**: [DvAauxSrcPack1](Properties/CAPLfunctionDvAauxSrcPack1.md) - dword  
  AAUX source pack for the first audio block.

- **DvAauxCtrlPack1**: [DvAauxCtrlPack1](Properties/CAPLfunctionDvAauxCtrlPack1.md) - dword  
  AAUX source pack for the second audio block.

- **DvVauxSrcPack**: [DvVauxSrcPack](Properties/CAPLfunctionDvVauxSrcPack.md) - dword  
  Video auxiliary (VAUX) source control pack.

- **DvVauxCtrlPack**: [DvVauxCtrlPack](Properties/CAPLfunctionDvVauxCtrlPack.md) - dword  
  VAUX source pack.

The following attributes apply to Advanced Streaming Format (ASF) files.

- **ArbitraryFormat**: [ArbitraryFormat](Properties/CAPLfunctionArbitraryFormat.md) - byte[]  
  Additional format data for a binary stream in an ASF file.

- **ArbitraryHeader**: [ArbitraryHeader](Properties/CAPLfunctionArbitraryHeader.md) - byte[]  
  Type-specific data for a binary stream in an ASF file.

- **ImageLossTolerant**: [ImageLossTolerant](Properties/CAPLfunctionImageLossTolerant.md) - dword  
  Specifies whether an ASF image stream is a degradable JPEG type.

The following attributes apply to MPEG-4 files.

- **Mpeg4CurrentSampleEntry**: [Mpeg4CurrentSampleEntry](Properties/CAPLfunctionMpeg4CurrentSampleEntry.md) - dword  
  The index of the current entry in the sample description box.

- **Mpeg4SampleDescription**: [Mpeg4SampleDescription](Properties/CAPLfunctionMpeg4SampleDescription.md) - byte[]  
  The sample description box.

## Timestamp Time Properties

These properties can be applied to media types whose major type equals **MediaType_Timestamp**.

- **TimestampInterval**: [TimestampInterval](Properties/CAPLfunctionTimestampInterval.md) - dword  
  Number of events between each timestamp.

- **TimestampRate**: [TimestampRate](Properties/CAPLfunctionTimestampRate.md) - qword  
  Event rate for the timestamp stream.

- **TimestampType**: [TimestampType](Properties/CAPLfunctionTimestampType.md) - dword  
  Event type for the timestamp stream.

[Media CAPL Functions](CAPLfunctionsMediaOverview.md) • [Major Media Types / Audio Subtypes](CAPLfunctionsMediaMajorMediaTypesSubtypes.md)
