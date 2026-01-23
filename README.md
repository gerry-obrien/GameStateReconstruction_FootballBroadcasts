# Game State Reconstruction for Football Broadcasts (SoccerNetGS)

This repository contains our **Foundations of Deep Learning** project on reconstructing football game state from broadcast frames using a two-stage pipeline:

1. **YOLOv8 object detection** to localize key entities (players, goalkeepers, referees, ball, other).
2. **ResNet18 crop-based classification** to assign detected **players/goalkeepers** to **Left vs Right** teams.


## 🎬 Qualitative results (videos)
Project page with embedded clips (validation + test):  
https://gerry-obrien.github.io/GameStateReconstruction_FootballBroadcasts/

YouTube backups (unlisted):
- Validation clip: https://youtu.be/lexA9WE-dog
- Test clip: https://youtu.be/N37B-oxOJd8  

Overlay format:
- YOLO: `<class> <yolo_conf>`
- Players/goalkeepers additionally: `TEAM {Left/Right} {team_conf}` where `team_conf` is the ResNet softmax probability for the predicted team.

## 🧪 Models and evaluation summary
- **YOLOv8**: strong detection for large objects (players/referees/goalkeepers); **ball detection is the main bottleneck**.
- **ResNet18 team classifier**: moderate validation accuracy; shows an asymmetric error pattern (more `right → left` mistakes), which affects team overlays on test footage.

Full quantitative results and plots are reported in the accompanying write-up.
## 📚 Dataset
We use **SoccerNetGS** (GameState) frames and labels. Please follow the SoccerNet terms of use and dataset download instructions. This repository does not redistribute the dataset.

## 👥 Authors
- *G. O'Brien*  
- *A. Le Saux*
- *H. Boisson*
- *G. Emmanuel*
