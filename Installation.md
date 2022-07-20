# 🛠️ Installation

GRUB themes are all installed the same way. Some themes may provide an install script, feel free to use it if you want, it should just take the same actions described here. Some theme pages recommend using GRUB Customizer, I do not. It changes your GRUB config files and can make it difficult to apply tweaks or changes.

Click the title of the Theme you want to install and you should be taken to its page: Either on Pling or Github. Pling will have a Files tab right below the preview screenshot, Github should have a green CODE button you can click to clone the repo. Some themes are stored in folders of a larger repo, if you copy the URL and paste it into Gitzip (Check the *Useful Links* section) you can download just those files, rather than cloning the entire repo.

Once you have the theme files, it's just a simple matter of dropping them into a folder in **/boot/grub/themes**. You may need to change the owner of this folder to interact with it, using the command `sudo chown $USER /boot/grub/themes`. You should now have a folder in the themes directory named after the theme, and that folder should include the theme.txt and any other relevant files that theme came with.  

Once the theme is in place, you just need to set GRUB to use it. Navigate to **/etc/default** and edit the **grub** file in there. You'll require Root permissions for this, you can use the sudoedit command to easily open it in your terminal. It's not a difficult edit either way, you won't need to use the terminal editor for long. Find the `GRUB_THEME=` line and add the path to the theme.txt of the theme you want to use. Don't forget to change the `#GRUB_GFXMODE=` line to your desired resolution, removing the `#` to enable it.  
Finally, run the command `sudo update-grub` to finalize your changes. You need to run this command every time you make changes to a config file. (If you're on Fedora, the command is `sudo grub2-mkconfig -o /boot/grub2/grub.cfg` instead)

Upon restart, you should find your new theme will be used for your bootloader!
