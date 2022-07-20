# Intro
There are many great community made GRUB themes to spice up your bootloader before booting into your system proper. Unfortunately, they're spread across multiple sites and it can be difficult to find good ones. As another user told me, the majority of themes on Pling (the largest host of GRUB themes currently) are fairly low effort and can be boring to trawl through. Hence, I decided to put together this page to bring attention to some decent themes I've found around the internet over time. They aren't all absolute masterpieces of course: But they've all at least had a fair amount of effort put into them, with custom backgrounds, fonts, and colours.

And don't forget, themes are extremely easy to customize. Like a theme's layout but prefer a different background? Just replace the image in its folder with one of your own. Don't like the positioning of a theme's elements? Open the theme.txt and change their values. Want a different colour scheme? They're all set by HEX Values, which you can swap out in seconds. You can even convert almost any font to the type GRUB uses with the grub-mkfont command, then change the `item_font` line in the theme.txt to use it.  
Heck, you may even make enough changes to justify releasing your own separate theme entirely! Documentation on theming GRUB is pretty lacking, so there's no better way to learn than taking someone else's theme and examining how they set things out the way they did. 

# Installation
GRUB themes are all installed the same way. Some themes may provide an install script, feel free to use it if you want, it should just take the same actions described here. Some theme pages recommend using GRUB Customizer, I do not. It changes your GRUB config files and can make it difficult to apply tweaks or changes.

Click the title of the Theme you want to install and you should be taken to its page: Either on Pling or Github. Pling will have a Files tab right below the preview screenshot, Github should have a green CODE button you can click to clone the repo. Some themes are stored in folders of a larger repo, if you copy the URL and paste it into Gitzip (Linked further down) you can download just those files, rather than cloning the entire repo.

Once you have the theme files, it's just a simple matter of dropping them into a folder in **/boot/grub/themes**. You may need to change the owner of this folder to interact with it, using the command `sudo chown $USER /boot/grub/themes`. You should now have a folder in the themes directory named after the theme, and that folder should include the theme.txt and any other relevant files that theme came with.  

Once the theme is in place, you just need to set GRUB to use it. Navigate to **/etc/default** and edit the **grub** file in there. You'll require Root permissions for this, you can use the sudoedit command to easily open it in your terminal. It's not a difficult edit either way, you won't need to use the terminal editor for long. Find the `GRUB_THEME=` line and add the path to the theme.txt of the theme you want to use. Don't forget to change the `#GRUB_GFXMODE=` line to your desired resolution, removing the `#` to enable it.  
Finally, run the command `sudo update-grub` to finalize your changes. You need to run this command every time you make changes to a config file. (If you're on Fedora, the command is `sudo grub2-mkconfig -o /boot/grub2/grub.cfg` instead)

Upon restart, you should find your new theme will be used for your bootloader!

# Useful Links

[GRUB-Tweaks](https://github.com/VandalByte/grub-tweaks) - Multiple guides on various tweaks and additions you can make to further customize, or repair, your GRUB install.  
[Gitzip](https://kinolien.github.io/gitzip/) - Download individual folders and files from Github repositories without having to download the entire repo. Asks for a Token, but seems to work without just fine.

# Contributing
Contributions are very welcome, either of themes you've created yourself or just ones you've discovered online. Just open a Pull Request adding it to the Table with a preview image. If you're not sure how, just open an Issue with the link and preview image included, and I'll add it myself when I get the chance. That said, there are four rules on what will be accepted:

* **The majority of elements must be changed from default:** Themes that consist of the default GRUB menu with just a background thrown in will not be accepted. In the least please try to include a custom background, menu selector and flavor text.
* **Forks of existing themes must be recognizably different from their original:** I recommended altering elements of existing themes earlier, but if you wish to share an edited theme here, please ensure you've changed enough of it to stand out against the original. This page was created to make it easier to find unique themes, and that falls apart if every theme is a vague alteration to an existing one. Compare my CRT-Amber theme to the Fallout theme that it's forked from, for instance.
* **No Waifu themes**: Anime related themes are fine, but please, no themes revolving entirely around generic renders of an anime character. Pling has hundreds of these in every category, not just GRUB. They only appeal to audiences who have seen their particular show, in an already niche audience of people trying to customize their GRUB. Again, Anime is fine, this is just a rule against themes that consist of a few fancy colours and a single image of an anime character.
* **SFW only**: You'd think this is obvious, but you'd be surprised.

# Themes

>If you like a theme, please do consider giving it a rating on Pling or starring its repo on Github. It's very rare for anyone to rate on Pling and that's half the reason good themes are so hard to find. Plus, it always feels nice to see that people are enjoying the product you created.

|    |    |    |
|:-------:|:-------:|:---------:|
|<img src="/Images/Linux_Mind.png" width="400">|<img src="/Images/Descent.jpg" width="400">|<img src="/Images/SteamOS.png" width="400">|
|[**Linux Mind**](https://www.pling.com/p/1397139/)|[**Descent**](https://www.pling.com/p/1000083/)|[**SteamOS (Personalized)**](https://github.com/LegendaryBibo/Steam-Big-Picture-Grub-Theme)|
|<img src="/Images/Virtuaverse.png" width="400">|<img src="/Images/Yorha.png" width="400">|<img src="/Images/CRT-Amber.png" width="400">|
|[**Virtuaverse**](https://github.com/Patato777/dotfiles/tree/main/grub)|[**YoRHa**](https://github.com/OliveThePuffin/yorha-grub-theme)|[**CRT-Amber**](https://www.pling.com/p/1727268/)|
|<img src="/Images/Matter.gif" width="400">|<img src="/Images/Dedsec.gif" width="400">|<img src="/Images/Sekiro.png" width="400">|
|[**Matter (Customizable)**](https://www.pling.com/p/1400298/)|[**DedSec (Set)**](https://www.pling.com/p/1569525/)|[**Sekiro**](https://github.com/semimqmo/sekiro_grub_theme)|
|<img src="/Images/BigSur.png" width="400">|<img src="/Images/Fallout.png" width="400">|<img src="/Images/Graphite.png" width="400">|
|[**BigSur**](https://www.pling.com/p/1443844/)|[**Fallout**](https://www.pling.com/p/1230882/)|[**Graphite**](https://www.pling.com/p/1676418/)|
|<img src="/Images/Cyberpunk2077.png" width="400">|<img src="/Images/CyberRe.png" width="400">|<img src="/Images/Cyberpunk.png" width="400">|
|[**Cyberpunk 2077**](https://www.pling.com/p/1515662/)|[**CyberRe**](https://www.pling.com/p/1420727/)|[**Cyberpunk**](https://www.pling.com/p/1429443/)|
|<img src="/Images/GutsBlack-ArchLinux.png" width="400">|<img src="/Images/Sayonara.png" width="400">|<img src="/Images/Breeze.png" width="400">|
|[**GutsBlack ArchLinux**](https://forums.archlinux.fr/viewtopic.php?t=11361)|[**Sayonara**](https://github.com/samoht9277/dotfiles/tree/master/grub/themes/sayonara)|[**Breeze**](https://www.pling.com/p/1000111/)|
|<img src="/Images/Plasma-Dark.png" width="400">|<img src="/Images/Deadora.png" width="400">|<img src="/Images/Plasma-Light.png" width="400">|
|[**Plasma-Dark**](https://www.pling.com/p/1195799/)|[**Deadora**](https://www.pling.com/p/1111550/)|[**Plasma-Light**](https://www.pling.com/p/1197062/)|
|<img src="/Images/Sleek.gif" width="400">|<img src="/Images/Atomic.png" width="400">|<img src="/Images/Aero.png" width="400">|
|[**Sleek (Set + Personalized)**](https://www.pling.com/p/1414997/)|[**Atomic**](https://www.pling.com/p/1200710/)|[**Aero**](https://www.pling.com/p/1112066/)|
|<img src="/Images/Standby.png" width="400">|<img src="/Images/Axiom.jpg" width="400">|<img src="/Images/Solarized-Dark.png" width="400">|
|[**Standby**](https://www.pling.com/p/1172610/)|[**Axiom**](https://www.pling.com/p/1111735/)|[**Solarized-Dark**](https://www.pling.com/p/1177401/)|
|<img src="/Images/Retro_GRUB.png" width="400">|<img src="/Images/CyberXero.png" width="400">|<img src="/Images/Distro.gif" width="400">|
|[**Retro GRUB**](https://www.pling.com/p/1568741/)|[**CyberXero**](https://www.pling.com/p/1502415/)|[**Distro Themes (Set)**](https://www.pling.com/p/1482847/)|
|<img src="/Images/Poly-Light.png" width="400">|<img src="/Images/Solstice.jpg" width="400">|<img src="/Images/Poly-Dark.png" width="400">|
|[**Poly Light**](https://www.pling.com/p/1176413/)|[**Solstice**](https://www.pling.com/p/1111874/)|[**Poly Dark**](https://www.pling.com/p/1230780/)|
|<img src="/Images/Dark_Matter.gif" width="400">|<img src="/Images/Virtual_Future.png" width="400">|<img src="/Images/Grubby_Terminal.jpg" width="400">|
|[**Dark Matter (Set)**](https://www.pling.com/p/1603282/)|[**Virtual Future**](https://www.pling.com/p/1529571/)|[**Grubby Terminal**](https://gitlab.com/perthshiretim/grubby-terminal)|
|<img src="/Images/Billys_Agent.png" width="400">|<img src="/Images/Arcade.png" width="400">|<img src="/Images/Placeholder.png" width="400">|
|[**Billy's Agent**](https://gitlab.com/Drorago/billys-agent-grub2-theme)|[**Arcade**](https://github.com/nobreDaniel/dotfile)|-|
