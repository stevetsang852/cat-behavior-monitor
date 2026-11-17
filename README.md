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

## Free Test Videos (Pixabay)

Download these free videos and place them in `/media/frigate/` for the demo:

- [Cat Eating 1](https://pixabay.com/videos/cat-eating-food-eat-cute-portrait-205070/) — place as `cat_eating.mp4`
- [Cat Eating 2](https://pixabay.com/videos/cat-pet-animal-kitten-feline-256770/) — place as `cat_eating2.mp4`

More free videos: [Pixabay Cat Eating](https://pixabay.com/videos/search/cat%20eating/) | [Pexels Cat Eating](https://www.pexels.com/search/videos/cat%20eating/)

## Demo Files

- `demo/frigate-demo-config.yml` — Frigate config using looped local videos + zones
- `demo/node-red-demo-flow.json` — Node-RED flow: Frigate MQTT event → zone filter → Telegram

### How to run the demo

1. Download free videos above into Frigate media folder.
2. Copy `demo/frigate-demo-config.yml` into your Frigate config.
3. Import `demo/node-red-demo-flow.json` into Node-RED and configure MQTT + Telegram bot.
4. Start Frigate → events will trigger Telegram notifications.

## Public Datasets for Training / Testing

- [AP-10K](https://github.com/AlexTheBad/AP-10K) — Animal pose estimation
- Animal-Pose
- Oxford-IIIT Pet Dataset

## Status

Demo config and Node-RED flow added. Ready for local video testing.
