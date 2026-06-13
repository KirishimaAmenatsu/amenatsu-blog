+++
date = '2026-06-13T21:43:48+08:00'
draft = false
title = "Galgame's Love and Pain with Gamescope on Linux"
+++
# Intro
While playing *MysteryLover:Nonexistent Truth*, something hit  me: the noise from the fans of my laptop were extremely loud, so I inspected the working state of my device:
```
$ nvidia-smi 
Sat Jun 13 21:16:00 2026       
+-----------------------------------------------------------------------------------------+
| NVIDIA-SMI 610.43.02              KMD Version: 610.43.02     CUDA UMD Version: 13.3     |
+-----------------------------------------+------------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |
|                                         |                        |               MIG M. |
|=========================================+========================+======================|
|   0  NVIDIA GeForce RTX 5070 ...    Off |   00000000:01:00.0 Off |                  N/A |
| N/A   51C    P4             29W /  100W |     339MiB /  12227MiB |     18%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+

+-----------------------------------------------------------------------------------------+
| Processes:                                                                              |
|  GPU   GI   CI              PID   Type   Process name                        GPU Memory |
|        ID   ID                                                               Usage      |
|=========================================================================================|
|    0   N/A  N/A          166340    C+G   ...ery Lover 2\MysteryLover2.exe        300MiB |
+-----------------------------------------------------------------------------------------+

```
WHAT'S THIS???  

A Galgame occupied 18% of 5070Ti?  

All right, let's run it with mangohud to inspect on its FPS. 
![galgame in 240 FPS](/images/galgame-on-linux/240fps.png)
An e-sports-level galgame, I told myself. 

# Solution

After searching on ArchWiki and numerous trials and errors, a solution finally came up.  

**Gamescope**.  

[Gamescope](https://github.com/ValveSoftware/gamescope), a micro-compositor by Valve, is suitable for these occasions. 
Run games from Steam using Gamescope by changing  the games launch options like this:  

    gamescope -w YOUR_PREFERRED_WIDTH -h YOUR_PREFERRED_HEIGHT -W YOUR_PREFERRED_WIDTH -H YOUR_PREFERRED_HEIGHT -r 60 -e -- %command%
This would restrict its FPS to 60, while setting width and height of game and gamescope. 
It should be stressed that the arguments of `-h` `-H` and `-w` `-W` should be the same, otherwise the cursor in the Gamescope and that on your screen might not be at the same position.   

After that, the performance comsumption of the game went back to normal. 
![normal gaming](/images/galgame-on-linux/normal-game.png)

