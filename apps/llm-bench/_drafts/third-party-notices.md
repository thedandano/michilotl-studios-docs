---
layout: default
title: LLM Bench Third-Party Notices
description: Draft third-party notices for LLM Bench.
---

# LLM Bench Third-Party Notices

LLM Bench uses open-source software and can interoperate with model runtimes and model sources maintained by third parties.

This page is a launch draft. Before publishing, verify the exact license text and notice obligations against the dependency versions shipped in the submitted build.

## Runtime And Dependency Notice Checklist

- LiteRT-LM / LiteRTLM Swift wrapper - verify Apache-2.0 notice obligations.
- llama.cpp / LlamaFramework wrapper - verify MIT license notice obligations.
- ExecuTorch - verify the exact BSD-style license text and current dependency status.
- MLX Swift / MLX examples stack - verify MIT license notice obligations.
- PostHog iOS SDK - verify license notice obligations.

## Model And Source Names

Gemma, Qwen, Apple Intelligence, Hugging Face, Unsloth, and MLX names are used only to identify benchmark targets, runtimes, and download sources.

LLM Bench is not affiliated with, endorsed by, or sponsored by Apple, Google, Meta, Alibaba, Hugging Face, Unsloth, or MLX.

## Release Gate

Before publishing this page:

- Confirm every shipped runtime dependency and package source.
- Include required license text and copyright notices.
- Include Apache-2.0 NOTICE content where required.
- Remove dependencies that are not shipped in the submitted build.
- Keep trademark language factual and non-endorsing.
