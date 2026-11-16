# Cat Behavior Monitor

AI-powered cat behavior monitoring system using Mac mini, Tapo cameras, Frigate, and custom models.

## Goals

- Detect cat eating, drinking, litter box use
- Individual cat identification
- Activity logging and health alerts
- Telegram / Discord notifications

## Recommended Phased Approach

### Phase 1: Zone-based (No training required)
- Frigate + Zones
- Cat enters food zone > 60s → Eating
- Cat enters litter zone > 45s → Toilet
- Node-RED → Telegram notifications

### Phase 2: Individual cat recognition
- Frigate Object Classification (preferred)
- Or fine-tune YOLOv8 on your own cats

### Phase 3: Pose / behavior (optional)
- Use public datasets: AP-10K, Animal-Pose, Oxford-IIIT Pet

## Hardware

- Mac mini (M2/M4)
- Tapo C220 or C250 × 2 (food bowl + litter box)

## Public Datasets for Training / Testing

- [AP-10K](https://github.com/AlexTheBad/AP-10K) — Animal pose estimation
- Animal-Pose
- Oxford-IIIT Pet Dataset

## Status

Initial repository created. Ready for training scripts and test videos.
