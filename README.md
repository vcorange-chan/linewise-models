# Linewise native model resources

This repository contains versioned model resources, license notices, origin notes and checksums. It does not contain the private Linewise application source, credentials, user recordings or transcripts.

## English forced alignment

`english-ls960.onnx` is an English wav2vec 2.0 / CTC forced-alignment model exported from TorchAudio's `WAV2VEC2_ASR_BASE_960H`. It maps supplied English text to audio; it is not a text-generation model or a transcription API.

- Asset version: `english-ctc-ls960-v1`
- Size: 377856217 bytes
- SHA-256: `00425739055e2357b9f76ddbaba10d5cb1232cbb6fb263390b084495cf456952`
- Compatibility: self-contained FP32 ONNX opset 17 with `linewise-ctc-onnx-ls960-v1` metadata and 29 English CTC labels.
- Runtime: native ONNX Runtime; Python and PyTorch are not required for application use.

The developer export uses the official TorchAudio 2.7 checkpoint and projects the fairseq auxiliary axes to the English label set. Output quality still depends on the recording and supplied text. Structural validation and matching a checksum do not establish correct timing for every recording.

## Upstream and license

TorchAudio documents the original model as MIT-licensed and redistributed under that license: https://docs.pytorch.org/audio/2.7.0/generated/torchaudio.pipelines.WAV2VEC2_ASR_BASE_960H.html

Original checkpoint: https://download.pytorch.org/torchaudio/models/wav2vec2_fairseq_base_ls960_asr_ls960.pth

Original checkpoint SHA-256: `488fd4f16de84438ffc945334278c1b9fb9b7159a806c1080b16111a958c945d`.

Upstream fairseq source and copyright notice: https://github.com/facebookresearch/fairseq

See `LICENSE-MIT.txt`. Preserve the notice when redistributing this model. Releases are versioned; clients verify the pinned SHA-256 before accepting a download.

