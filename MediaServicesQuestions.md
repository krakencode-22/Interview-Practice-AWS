# Technical Interview Prep (First 10 Questions)  

---

## **Basic Questions**  

### 1. **What is a codec?**  
**Answer:**  
A codec (coder-decoder) compresses and decompresses digital video. Examples: H.264 (AVC), H.265 (HEVC), AV1. Compression reduces file size; decompression enables playback.  

---

### 2. **What is a bitrate ladder?**  
**Answer:**  
A set of video streams at different resolutions/bitrates (e.g., 480p@1.5Mbps, 1080p@6Mbps). Enables adaptive streaming by switching qualities based on network conditions.  

---

### 3. **Define CBR and VBR. When would you use each?**  
**Answer:**  
- **CBR (Constant Bitrate):** Fixed bitrate for stable bandwidth (live streaming). Sacrifices quality in complex scenes.  
- **VBR (Variable Bitrate):** Adjusts bitrate for optimal quality (VOD). Uses more bits for high-motion scenes.  

---

### 4. **Compare chroma subsampling schemes: 4:2:0 vs. 4:4:4.**  
**Answer:**  
- **4:4:4:** Full color resolution (pro workflows like green screen).  
- **4:2:0:** Halved color resolution (standard for streaming). Saves ~33% bandwidth with minimal quality loss.  

---

### 5. **What is a GOP (Group of Pictures)? Define I, P, and B frames.**  
**Answer:**  
A **GOP** starts with an **I-frame** (standalone), followed by:  
- **P-frames:** Predict from previous frames.  
- **B-frames:** Predict from past and future frames.  
Shorter GOPs improve seekability; longer GOPs save bits.  

---

## **Intermediate Questions**  

### 6. **Compare H.264, H.265, and AV1 in compression efficiency and use cases.**  
**Answer:**  
- **H.264:** Standard for 1080p (broad compatibility).  
- **H.265:** ~50% better efficiency (4K). Licensing fees apply.  
- **AV1:** Royalty-free, ~30% better than HEVC. Requires modern hardware.  

---

---

### 7. **What factors determine codec adoption (e.g., H.265 vs. AV1)?**  
**Answer:**  
- **Device compatibility:** H.265 is widely supported; AV1 requires newer hardware.  
- **Licensing costs:** HEVC has royalties; AV1 is free.  
- **Compute resources:** AV1 encoding is slower/more intensive.  
- **Use case:** 4K/HDR favors HEVC; open-source projects prefer AV1.  

---

### 8. **What are the key differences between HLS and DASH?**  
**Answer:**  
- **HLS (HTTP Live Streaming):** Apple’s protocol (M3U8 manifests), uses TS/CMAF chunks. Favors iOS/macOS.  
- **DASH (Dynamic Adaptive Streaming over HTTP):** Open standard (MPD manifests), codec-agnostic. Preferred for Android/Web.  
- **Latency:** LL-HLS vs. LL-DASH for sub-3s streaming.  

---

### 9. **Explain rate control methods: CBR, VBR, and CRF.**  
**Answer:**  
- **CBR (Constant Bitrate):** Fixed bitrate (live streaming). Ensures stable bandwidth but sacrifices quality in complex scenes.  
- **VBR (Variable Bitrate):** Dynamic bitrate (VOD). Prioritizes quality but risks bitrate spikes.  
- **CRF (Constant Rate Factor):** Quality-focused VBR (0–51 scale). Balances file size and quality (e.g., CRF 18–23 for 1080p).  

---

### 10. **What is HDR’s impact on video encoding?**  
**Answer:**  
HDR (High Dynamic Range) requires:  
- **10-bit color depth** (vs. 8-bit for SDR).  
- **Wider color gamut** (BT.2020 vs. BT.709).  
- **Higher bitrates** (~20Mbps for 4K HDR vs. 6Mbps for 1080p SDR).  
- **Tone mapping** for SDR fallback.

---

### 11. **What is adaptive bitrate streaming (ABR)?**  
**Answer:**  
ABR dynamically adjusts video quality (resolution/bitrate) based on the viewer’s network bandwidth. Players download smaller chunks (e.g., 6s segments) and switch between renditions (e.g., 720p to 1080p) to minimize buffering.  

---

### 12. **What is a CDN, and why is it critical for streaming?**  
**Answer:**  
A **CDN (Content Delivery Network)** caches video segments on geographically distributed edge servers. Reduces latency, improves scalability, and handles traffic spikes (e.g., live events). Examples: Akamai, CloudFront.  

---

### 13. **What is the purpose of a manifest file in streaming?**  
**Answer:**  
A manifest file (HLS: `.m3u8`, DASH: `.mpd`) lists available video segments, bitrates, codecs, and DRM information. It guides the player to adaptively switch between qualities.  

---

### 14. **What is DRM, and name common systems.**  
**Answer:**  
**DRM (Digital Rights Management)** encrypts content to prevent piracy. Common systems:  
- **Widevine** (Android/Web)  
- **FairPlay** (Apple devices)  
- **PlayReady** (Windows/Xbox)  

---

### 15. **What is a video codec profile (e.g., H.264 Baseline vs. High)?**  
**Answer:**  
A profile defines codec features and compatibility:  
- **Baseline (H.264):** Minimal features (mobile compatibility).  
- **High (H.264):** Advanced features (CABAC, B-frames) for Blu-ray/streaming.  

---

### 16. **How do you optimize encoding for low-bandwidth networks?**  
**Answer:**  
- Use efficient codecs (AV1/H.265).  
- Lower resolutions (480p) and bitrates (1.5Mbps).  
- Prioritize keyframes and reduce GOP length.  
- Enable faster presets (e.g., `-preset faster` in FFmpeg).  

---

### 17. **Explain multi-DRM workflow for cross-platform streaming.**  
**Answer:**  
Encrypt content once using **CENC (Common Encryption)** and integrate with:  
- **Widevine** (Android/Chrome)  
- **FairPlay** (iOS/Safari)  
- **PlayReady** (Windows/Edge)  
Use a DRM license server (e.g., Google’s Widevine Server) to manage keys.  

---

### 18. **How would you troubleshoot playback issues on a Smart TV?**  
**Answer:**  
1. Check device logs for decoder/DRM errors.  
2. Validate manifest alignment and CDN availability.  
3. Test with a reference stream (known working content).  
4. Verify network conditions (latency, packet loss).  

---

### 19. **What is a Just-in-Time (JIT) packager?**  
**Answer:**  
A JIT packager generates video segments on-demand during playback instead of pre-encoding. Reduces storage costs for rarely accessed content. Adds ~100–200ms latency.  

---

### 20. **What is the purpose of a video test lab?**  
**Answer:**  
A test lab validates playback across devices (Roku, Apple TV, mobile) and simulates network conditions (e.g., 3G throttling). Ensures compatibility and performance before deployment.  

---

### 21. **What is the difference between live streaming and VOD?**  
**Answer:**  
- **Live Streaming:** Real-time delivery (low latency, uses CBR). Examples: sports, concerts.  
- **VOD (Video on Demand):** Pre-recorded content (uses VBR/CRF). Examples: Netflix, YouTube.  

---

### 22. **What is a video segment in adaptive streaming?**  
**Answer:**  
A segment is a short chunk of video (e.g., 6 seconds) encoded at a specific bitrate. Players download segments sequentially to adapt to network changes.  

---

### 23. **What is a mezzanine file?**  
**Answer:**  
A high-quality master file (e.g., ProRes, DNxHR) used as the source for encoding. Retains maximum detail for transcoding to multiple formats.  

---

### 24. **What is a video container format (e.g., MP4, TS)?**  
**Answer:**  
A container (MP4, MKV, TS) stores video, audio, and metadata. MP4 is standard for streaming; TS is used in HLS for compatibility.  

---

### 25. **How does multi-pass encoding improve quality?**  
**Answer:**  
Multi-pass encoding analyzes the entire video in the first pass to optimize bitrate allocation. Reduces quality fluctuations (e.g., action scenes get more bits).  

---

### 26. **What is HEVC tile-based encoding?**  
**Answer:**  
HEVC tiles divide a frame into grids for parallel encoding/decoding. Improves performance for 8K/VR content and enables region-of-interest streaming.  

---

### 27. **How do you optimize for perceptual quality (e.g., VMAF)?**  
**Answer:**  
Use tools like Netflix’s VMAF to score perceived quality (0–100). Adjust CRF/bitrate ladders until VMAF > 90. Prioritize critical scenes (faces, motion).  

---

### 28. **Explain redundancy in live streaming workflows.**  
**Answer:**  
Deploy backup encoders (e.g., AWS Elemental + FFmpeg) and redundant CDN paths. Use RTMP failover and monitor with heartbeat checks to ensure 99.9% uptime.  

---
 

### 29. **What causes buffering during video playback?**  
**Answer:**  
Buffering occurs due to insufficient bandwidth, high latency, or CDN/server issues. The player pauses to download enough segments to refill the playback buffer.  

---

### 30. **What is the difference between MP4 and MKV containers?**  
**Answer:**  
- **MP4:** Industry standard for streaming (HLS/DASH). Supports fragmented streaming and DRM.  
- **MKV:** Open-source, flexible (supports multiple audio/subtitle tracks). Used for archival, not streaming.  

---

### 31. **Why is frame rate important in video streaming?**  
**Answer:**  
Higher frame rates (e.g., 60fps) improve smoothness for sports/action but increase bandwidth. Lower frame rates (24fps) save bandwidth but may cause stuttering.  

---

### 32. **What is a video thumbnail, and how is it generated?**  
**Answer:**  
A thumbnail is a preview image extracted from a video. 


---

### 33. **What is the role of a load balancer in streaming?**  
**Answer:**  
A load balancer distributes traffic across multiple servers to prevent overload during high demand (e.g., live events). It ensures high availability, reduces latency, and scales resources dynamically. Tools: AWS Elastic Load Balancer, NGINX.  

---

### 34. **How do you optimize encoding for VR/360-degree video?**  
**Answer:**  
- Use **equirectangular projection** and high bitrates (50Mbps+).  
- Leverage **tile-based encoding** (HEVC/AV1) to stream only viewed regions.  
- Ensure low motion-to-photon latency (<20ms) for immersive experiences.  

---

### 35. **Explain dynamic ad insertion (DAI) in live streams.**  
**Answer:**  
DAI inserts ads in real-time using **SCTE-35 markers** to trigger ad breaks. Requires:  
- **Ad decision server** (e.g., Google Ad Manager).  
- **Frame-accurate packaging** (AWS MediaTailor).  
- Monitoring for ad alignment and viewer experience.  

---

### 36. **How do you monitor streaming QoS (Quality of Service)?**  
**Answer:**  
Track metrics:  
- **Rebuffering rate** (<2%).  
- **Average bitrate** vs. requested bitrate.  
- **Playback failures** (DRM errors, segment timeouts).  
Tools: Datadog, Conviva, Mux Data.  

---

### 37. **What strategies reduce latency in live streaming?**  
**Answer:**  
- **Low-Latency HLS/DASH** (chunked CMAF, HTTP/2 push).  
- **Ultra-short GOPs** (1–2 seconds).  
- **Edge packaging** (AWS MediaPackage, Unified Origin).  
- **WebRTC** for sub-500ms glass-to-glass latency.  

---

### 38. **How do you implement disaster recovery for streaming?**  
**Answer:**  
- **Multi-CDN failover** (e.g., CloudFront + Akamai).  
- **Redundant encoders** (AWS Elemental + on-prem FFmpeg).  
- **Geo-replicated storage** (S3 Cross-Region Replication).  
- **Automated health checks** (e.g., AWS CloudWatch).

### 39. **What is the difference between 1080i and 1080p?**  
**Answer:**  
- **1080i (Interlaced):**  
  Displays video in two alternating fields (odd/even lines), reducing bandwidth but causing motion artifacts (e.g., "combing"). Used in broadcast TV.  
- **1080p (Progressive):**  
  Displays all lines sequentially, delivering smoother motion and sharper details. Standard for streaming (Netflix, YouTube) and Blu-ray.  

**Key Difference:**  
- **Interlaced (i):** Better for bandwidth-limited live broadcasts.  
- **Progressive (p):** Superior for high-motion content and modern streaming.