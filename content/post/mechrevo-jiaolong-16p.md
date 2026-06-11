+++
date = '2026-06-11T20:09:53+08:00'
draft = false
title = 'ArchLinux On Mechrevo JiaoLong 16Pro 2026: Exceptionally Wonderful'
+++
# Reason
The College Entrance Examination has ended, and most students, including me, would purchase a set of electronic devices after that.  

For laptop,I chose **JiaoLong 16Pro 2026** , due to its low price(relatively speaking, comparing with ASUS Tianxuan 7ProMax). With roughly CNY10200 (with national grant and JDPlus), you can get a laptop equipped with **AMD Ryzen 9 8945HX**, **NVIDIA 5070Ti Laptop**, alone with **32 GB DDR5 memory**, which can be cost-effective given memories prices nowadays.

# Hesitation
However, I've read some infomation on the Internet about Mechrevo. It is reported that this band comes with poor quality control. By the way, some models of this brand is equipped with  YT6801 (1f0a:6801) [^1] Ethernet controler, whose driver isn't in-tree. However, it's truly ***appealing*** , so, I purchased it.

# Hardware details
| Type | ID | Status|
| --- | --- | --- |
| Keyboard | PS/2 | Working |
| Touchpad | PS/2 | Working |
| iGPU(AMD) | 1002:164e | Working |
| dGPU(NVIDIA) | 10de:2f18 | Out-tree Driver required |
| MT7922 Wireless Network Adapter | 14c3:7922 | Working |
| RTL8125 Ethernet Controller | 10ec:8125 | Working |
| Bluetooth | 13d3:3585 | Working |
| Audio | 1022:15e3 | Working |
| Keyboard Backlight | | Out-tree Driver required |

It's a satisfying result. I guessed that the ethernet controller cannot work, but it can! NVIDIA GPU requires non-free driver, but it's the fault of NVIDIA.

# Installation of ArchLinux
To prevent my privacy, I used dm-crypt and secure boot, which made the installation process a little exhasutant. But I don't have a hardware security key, and I don't trust TPM very much. Just passphrases isn't a good plan.   

To fully function it's hardware, for instances, keyboard backlight, I suggest install `mechrevo-drivers-dkms` and `tuxedo-control-center-bin` AUR package. Its model is the same as some of Tuxedo, which makes these possible. And I think the `tuxedo control center` is better than the control center of Mechrevo in Windows---you can input CSS color code instead of just rolling the slider.

# Summary 
It is a truly good laptop for these following reasons:
- Low Price
- Available Driver for Linux

But it also have some cons, for example, the noise when the fans are working.  

# Footnotes
[^1]:  https://wiki.archlinux.org/title/Mechrevo_WUJIE14X