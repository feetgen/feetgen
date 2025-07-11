
[➡️ Visit FeetGen Live](https://feet-gen.com)

---

# FeetGen – AI Feet Image Generator

> “Teaching machines to understand anatomy—starting at the toes.”  
> **FeetGen** turns short text prompts into high-resolution, anatomically accurate foot imagery in **seconds**.  
> Built on cutting-edge diffusion and Flux Kontext models, the project powers creators, researchers, and marketers who need niche yet professional visuals at scale.

---

## Badges

![License: MIT](https://img.shields.io/badge/license-MIT-blue.svg)
![Build](https://img.shields.io/github/actions/workflow/status/feet-gen/feetgen/ci.yml)
![Coverage](https://img.shields.io/codecov/c/github/feet-gen/feetgen)

---

## TL;DR

* **Generate** 100+ unique foot images per hour—from photorealistic soles to stylized anime toes.  
* **Customize** every detail (pose, lighting, style) in real time.  
* **Deploy** the API on-prem or serverless; or run our slick Next.js web UI out-of-the-box.  
* **License-safe**: all outputs come with commercial usage rights.  
* **Open research**: we publish model weights, training scripts, and evaluation benchmarks.

---

## Table of Contents
1. [The 5W1H](#the-5w1h)
2. [Features](#features)
3. [License](#license)
4. [Community & Support](#community--support)
5. [FAQ](#faq)

---

## The 5W1H

### Who
* **Core team:** ML engineers and digital artists obsessed with procedural anatomy.  
* **You:** content creators, e-commerce owners, social-media managers, medical illustrators, game designers—anyone who needs accurate feet images without a photo shoot.

### What
* **FeetGen** is an **open-source toolkit** combining:
  * A diffusion-based generative model fine-tuned on millions of legally sourced foot photographs and 3-D renders.
  * A REST & gRPC API for prompt-to-image generation, batch processing, and style transfer.
  * A Next.js + Tailwind CSS web application for zero-code experimentation.
  * Python & JavaScript client SDKs.

### When
* Use FeetGen when you:
  1. Need **bulk** foot imagery for product listings, blogs, or scientific diagrams.
  2. Want to **prototype** foot-centric AR/VR assets fast.
  3. Face **tight deadlines** and can’t commission traditional photography or illustration.  
  4. Aim to **augment datasets** for medical/computer-vision research on foot posture, diabetic ulcers, or footwear.

### Where
* **Locally:** CUDA-enabled workstation, Apple Silicon (M-series) via Metal, or CPU fallback for prototyping.  
* **Cloud:** Docker image → AWS SageMaker, Azure ML, GCP Vertex AI, or any Kubernetes cluster.  
* **Edge:** ONNX-quantized variant runs on iOS/Android with Core ML / NNAPI.

### Why
* **Niche ≠ trivial.** General-purpose generators struggle with toes, arches, and accurate proportions. FeetGen’s domain-specific corpus fixes that.  
* **Privacy & compliance.** Generate synthetic datasets without handling personal images.  
* **Cost.** Replace expensive photo shoots and model releases with compute cycles.  
* **Creativity.** Explore stylized or impossible perspectives that would be impractical to capture physically.

### How
1. **Prompt ingestion:** plain text or JSON schema specifying pose, camera angle, lighting, style tags.  
2. **Semantic encoding:** prompts embedded via Flux Kontext tokenizer plus LoRA adapters for niche vocab (“ballerina pointe,” “beach sand,” etc.).  
3. **Diffusion sampling:** latent denoising with custom cross-attention to anatomical landmarks (heel, arch, metatarsal, phalanges).  
4. **Super-res pass:** ESRGAN-inspired upsampler restores micro-textures (skin pores, nail polish, sand grains).  
5. **Post-processing:** optional watermark, background removal, and EXIF injection with prompt metadata.  
6. **Delivery:** signed URL, base64, or direct S3/GCS upload.

---

## Features

| Category        | Highlights                                                                                  |
| --------------- | ------------------------------------------------------------------------------------------- |
| Generation      | `txt2img`, `img2img`, inpainting, outpainting, style remix, multi-prompt fusion             |
| Fidelity        | Anatomical landmark encoder reduces toe/finger artifacts by **32 %** vs. vanilla SD 2.1     |
| Speed           | Batch mode: **~0.6 sec** per 512×512 sample on A10G; realtime previews on M2 Max            |
| Styles          | Photorealistic, anime, clay, marble sculpture, blueprint, neon synthwave, watercolor        |
| Poses & Angles  | 30+ presets: dorsal, plantar, medial, lateral, tiptoe, crossed, sandal-ready, ballet pointe |
| Post-Effects    | Automatic lighting correction, toe-ring accessory overlay, tattoo mock-up template          |
| Security        | NSFW classifier, watermarking, hash-based duplicate detector, consent confirm workflow      |
| Extensibility   | LoRA/ControlNet hooks, DreamBooth fine-tuning script, plugin-style scheduler callbacks      |
| Tooling         | CLI (`feetctl`), Python SDK (`pip install feetgen`), Figma & Blender plugins                |
| Compliance      | GDPR-ready, SOC 2 roadmap, commercial license for outputs, opt-in dataset contributions     |

---


---

## License

`feetgen` is distributed under the MIT License.  
Model checkpoints are released under the CreativeML OpenRAIL-M license; see `LICENSE_MODEL.md` for usage restrictions.

---

## Community & Support

* Twitter: [@FeetGen](https://twitter.com/FeetGenAI)  
* Discord: `discord.gg/feetgen` (10k+ builders, nightly model drops)  
* Email: `support@feet-gen.com`  

Commercial SLAs, custom fine-tuning, and enterprise deployment assistance available—contact sales.

---

## FAQ

<details>
<summary><strong>Why a dedicated feet generator? Doesn’t Stable Diffusion already do this?</strong></summary>

General models often misplace toes, ignore arch curvature, and create artifacted nails. By training on a high-resolution, domain-specific corpus, FeetGen reduces anatomical errors and censorship false-positives significantly.
</details>

<details>
<summary><strong>Is it legal to use FeetGen images commercially?</strong></summary>

Yes. Outputs are released with a royalty-free commercial license. Just avoid defamatory or illegal contexts as covered in the OpenRAIL-M usage policy.
</details>

<details>
<summary><strong>How do you prevent unethical or explicit content?</strong></summary>

We run an NSFW classifier and content moderation queue. Custom prompts that violate terms are rejected with a 4xx code. Enterprise users can self-host with stricter filters.
</details>

<details>
<summary><strong>What hardware do I need?</strong></summary>

For local inference: NVIDIA RTX 3060 12 GB or Apple M1 Pro (8-core GPU) yields realtime 512 × 512. CPU mode works but is slow (~30 s per image).
</details>

<details>
<summary><strong>Can I fine-tune the model on my brand’s shoe line?</strong></summary>

Absolutely. Use the `scripts/dreambooth_ft.py` notebook. Fine-tuning on ~20 labeled product shots improves logo fidelity by 40 %.
</details>

<details>
<summary><strong>Where can I see example prompts?</strong></summary>

Check the [Gallery](https://feet-gen.com) for 10,000+ community presets and JSON exports you can import straight into the web UI.
</details>

<details>
<summary><strong>Does the project cover other body parts?</strong></summary>

FeetGen focuses on feet for now. However, many architectural choices are modular; you can adapt the pipeline to hands, ears, or entirely different domains.
</details>

---

Made with ❤️, ☕, and a lot of reference images.
