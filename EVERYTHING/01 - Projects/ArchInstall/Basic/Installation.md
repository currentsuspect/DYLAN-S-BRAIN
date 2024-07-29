### Arch Linux Installation Guide with Hyprland, Zsh, Vim, Tmux, and Ricing

Hey Dylan! Let's dive into a detailed guide to install Arch Linux from scratch with Hyprland as your desktop manager, Zsh as your shell, Vim as your text editor, Tmux as a multiplexer, EXT4 for your filesystem, and GRUB as your bootloader. This guide will be super detailed, so you can understand every step and make your system look awesome!

### Prerequisites
1. **Live USB**: You need an Arch Linux ISO and a tool like `dd` or `Etcher` to create a bootable USB.
2. **Internet Connection**: Ensure you have a stable internet connection.

### Step-by-Step Guide

#### 1. Boot from Live USB
- Insert the USB and boot your machine. Select the USB from the boot menu.

#### 2. Set Keyboard Layout (Optional)
- Default is US. If you need a different layout:
  ```sh
  loadkeys <your-keyboard-layout>
  ```

#### 3. Verify Boot Mode
- Check if you're in UEFI mode:
  ```sh
  ls /sys/firmware/efi/efivars
  ```
  If the directory exists, you're in UEFI mode.

#### 4. Connect to the Internet
- Use `iwctl` for Wi-Fi:
  ```sh
  iwctl
  ```
  Inside `iwctl`, use:
  ```sh
  device list
  station <device> scan
  station <device> get-networks
  station <device> connect <SSID>
  ```

- Verify connection:
  ```sh
  ping archlinux.org
  ```

#### 5. Update System Clock
- Sync the system clock:
  ```sh
  timedatectl set-ntp true
  ```

#### 6. Partition the Disk
- List disks:
  ```sh
  lsblk
  ```
- Use `fdisk` to partition:
  ```sh
  fdisk /dev/sdX
  ```
  Create partitions:
  - `efi` (for UEFI): 512M (Type: EFI System)
  - `root`: Remaining space (Type: Linux filesystem)

#### 7. Format the Partitions
- Format EFI partition:
  ```sh
  mkfs.fat -F32 /dev/sdX1
  ```
- Format root partition with EXT4:
  ```sh
  mkfs.ext4 /dev/sdX2
  ```

#### 8. Mount the Partitions
- Mount root:
  ```sh
  mount /dev/sdX2 /mnt
  ```
- Create and mount EFI:
  ```sh
  mkdir /mnt/boot
  mount /dev/sdX1 /mnt/boot
  ```

#### 9. Install Base System
- Install base packages:
  ```sh
  pacstrap /mnt base base-devel linux linux-firmware
  ```

#### 10. Configure the System
- Generate fstab:
  ```sh
  genfstab -U /mnt >> /mnt/etc/fstab
  ```

- Change root into the new system:
  ```sh
  arch-chroot /mnt
  ```

- Set the timezone:
  ```sh
  ln -sf /usr/share/zoneinfo/Region/City /etc/localtime
  hwclock --systohc
  ```

- Localization:
  ```sh
  echo "en_US.UTF-8 UTF-8" >> /etc/locale.gen
  locale-gen
  echo "LANG=en_US.UTF-8" > /etc/locale.conf
  ```

- Set hostname:
  ```sh
  echo "your_hostname" > /etc/hostname
  ```

- Configure hosts file:
  ```sh
  echo "127.0.0.1   localhost" >> /etc/hosts
  echo "::1         localhost" >> /etc/hosts
  echo "127.0.1.1   your_hostname.localdomain your_hostname" >> /etc/hosts
  ```

#### 11. Install Bootloader
- Install and configure GRUB:
  ```sh
  pacman -S grub efibootmgr
  grub-install --target=x86_64-efi --efi-directory=/boot --bootloader-id=GRUB
  grub-mkconfig -o /boot/grub/grub.cfg
  ```

#### 12. Create a User and Set Passwords
- Set root password:
  ```sh
  passwd
  ```

- Create a new user:
  ```sh
  useradd -m -G wheel -s /bin/zsh your_username
  passwd your_username
  ```

- Edit sudoers:
  ```sh
  visudo
  ```
  Uncomment:
  ```sh
  %wheel ALL=(ALL) ALL
  ```

#### 13. Install Essential Packages
- Network tools, Vim, and other essentials:
  ```sh
  pacman -S networkmanager vim zsh tmux git
  ```

- Enable NetworkManager:
  ```sh
  systemctl enable NetworkManager
  ```

#### 14. Install Graphics Drivers
- For Intel graphics:
  ```sh
  pacman -S xf86-video-intel
  ```

#### 15. Install Hyprland
- Install dependencies:
  ```sh
  pacman -S wayland weston xorg-server-xwayland \
             libxkbcommon libxkbcommon-x11 \
             xorg-xwayland wayland-protocols \
             vulkan-icd-loader libvulkan libva \
             mesa pavucontrol alsa-utils
  ```

- Install Hyprland:
  ```sh
  git clone https://github.com/hyprwm/Hyprland
  cd Hyprland
  make
  sudo make install
  ```

#### 16. Configure Hyprland
- Create Hyprland configuration:
  ```sh
  mkdir -p ~/.config/hypr
  vim ~/.config/hypr/hyprland.conf
  ```
  Add your configuration here (you can customize it as needed).

#### 17. Set Up Zsh
- Install Oh-My-Zsh:
  ```sh
  sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
  ```

- Customize `.zshrc`:
  ```sh
  vim ~/.zshrc
  ```
  Add your custom aliases, themes, and plugins.

#### 18. Set Up Tmux
- Basic Tmux configuration:
  ```sh
  vim ~/.tmux.conf
  ```
  Add configurations like setting prefix, status bar customization, etc.

#### 19. Rice Your System
- Install themes and fonts:
  ```sh
  pacman -S ttf-dejavu ttf-liberation noto-fonts
  ```

- Customize Hyprland with themes, wallpapers, and more:
  ```sh
  mkdir -p ~/.config/wallpapers
  wget -O ~/.config/wallpapers/your_wallpaper.jpg https://example.com/wallpaper.jpg
  ```

- Add more configurations to Hyprland:
  ```sh
  vim ~/.config/hypr/hyprland.conf
  ```

#### 20. Final Steps
- Exit chroot and unmount partitions:
  ```sh
  exit
  umount -R /mnt
  reboot
  ```

### Additional Tips
- Keep your system updated:
  ```sh
  sudo pacman -Syu
  ```

- Backup your configuration files:
  ```sh
  git init
  git remote add origin your_repo_url
  git add .
  git commit -m "Initial commit"
  git push -u origin master
  ```

That's it! You've got a fully set up Arch Linux system with Hyprland, Zsh, Vim, Tmux, and a riced environment. Enjoy the process, and feel free to tweak and customize as you see fit. If you have any questions or need further customization tips, just let me know!