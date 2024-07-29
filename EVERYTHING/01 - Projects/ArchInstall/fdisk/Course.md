Alright, Dylan! Let's dive deep into `fdisk`, a powerful command-line utility used for disk partitioning on Linux systems. We'll cover everything from the basics to advanced usage, so you can master `fdisk` and effectively manage your disk partitions.

### What is `fdisk`?

`fdisk` is a text-based utility for viewing and managing disk partitions on Linux. It can create, delete, resize, and manipulate disk partitions. It supports MBR (Master Boot Record) and GPT (GUID Partition Table) partitioning schemes.

### Installing `fdisk`

`fdisk` is part of the `util-linux` package, which is typically pre-installed on most Linux distributions. To ensure it's installed on your system, use:

```sh
sudo pacman -S util-linux
```

### Basic Usage of `fdisk`

#### 1. Launching `fdisk`

To start `fdisk`, use:

```sh
sudo fdisk /dev/sdX
```

Replace `/dev/sdX` with your actual disk (e.g., `/dev/sda`, `/dev/sdb`).

#### 2. Viewing Partition Table

Once inside `fdisk`, you can view the current partition table by typing:

```sh
p
```

This will display information about the partitions on the selected disk.

### Creating Partitions

#### 1. Creating a New Partition

To create a new partition, follow these steps:

1. **Enter `fdisk`:**

    ```sh
    sudo fdisk /dev/sdX
    ```

2. **Create a new partition:**

    - Type `n` to create a new partition.
    - Choose the partition type (`p` for primary, `e` for extended).
    - Select the partition number (1-4 for primary, 5+ for logical).
    - Specify the starting and ending sectors or accept the default values for maximum available space.

3. **Write the changes:**

    - Type `w` to write the changes to the disk.

#### 2. Formatting the Partition

After creating the partition, you need to format it with a filesystem. For example, to format as EXT4:

```sh
sudo mkfs.ext4 /dev/sdX1
```

Replace `/dev/sdX1` with your actual partition.

### Deleting Partitions

#### 1. Deleting a Partition

To delete an existing partition, follow these steps:

1. **Enter `fdisk`:**

    ```sh
    sudo fdisk /dev/sdX
    ```

2. **Delete the partition:**

    - Type `d`.
    - Enter the partition number to delete.

3. **Write the changes:**

    - Type `w` to write the changes to the disk.

### Advanced Usage

#### 1. Creating GPT Partitions

To use GPT instead of MBR, you need to specify it in `fdisk`:

```sh
sudo fdisk /dev/sdX
```

Inside `fdisk`, type:

```sh
g
```

This initializes the disk with a GPT partition table.

#### 2. Setting Partition Types

Each partition has a type that indicates its intended use. To set a partition type:

1. **Enter `fdisk`:**

    ```sh
    sudo fdisk /dev/sdX
    ```

2. **Set the partition type:**

    - Type `t`.
    - Enter the partition number.
    - Enter the hex code for the partition type (e.g., `83` for Linux filesystem, `82` for Linux swap).

#### 3. Resizing Partitions

`fdisk` itself does not resize partitions. To resize partitions, you can use `parted` or `gparted`. However, you can delete and recreate a partition with a different size using `fdisk`.

### Practical Examples

Let's go through practical examples of using `fdisk` to manage disk partitions.

#### Example: Creating a New Partition

1. **List disks:**

    ```sh
    lsblk
    ```

2. **Launch `fdisk`:**

    ```sh
    sudo fdisk /dev/sdX
    ```

3. **Create a new partition:**

    - Type `n`.
    - Choose `p` for primary.
    - Select partition number (e.g., `1`).
    - Accept default start and end sectors for full available space.
    - Type `w` to write changes.

4. **Format the partition:**

    ```sh
    sudo mkfs.ext4 /dev/sdX1
    ```

#### Example: Deleting a Partition

1. **Launch `fdisk`:**

    ```sh
    sudo fdisk /dev/sdX
    ```

2. **Delete the partition:**

    - Type `d`.
    - Enter partition number (e.g., `1`).
    - Type `w` to write changes.

#### Example: Creating a GPT Partition Table

1. **Launch `fdisk`:**

    ```sh
    sudo fdisk /dev/sdX
    ```

2. **Create GPT partition table:**

    - Type `g`.
    - Type `w` to write changes.

3. **Create a new GPT partition:**

    - Type `n`.
    - Follow prompts to create a new partition.
    - Type `w` to write changes.

### Common `fdisk` Commands

Here's a list of common `fdisk` commands and their usage:

- `p`: Print the partition table.
- `n`: Add a new partition.
- `d`: Delete a partition.
- `t`: Change a partition's type.
- `l`: List known partition types.
- `w`: Write table to disk and exit.
- `q`: Quit without saving changes.
- `m`: Display help.

### Scripting with `fdisk`

`fdisk` commands can be scripted for automation. For example, a script to create a new partition could look like this:

```sh
#!/bin/bash

DISK="/dev/sdX"

echo -e "n\np\n1\n\n\nw" | fdisk $DISK
mkfs.ext4 ${DISK}1
```

Make the script executable and run it:

```sh
chmod +x create_partition.sh
sudo ./create_partition.sh
```

### Conclusion

You've now covered a comprehensive course on using `fdisk` for disk partitioning on Linux. From basic commands to advanced usage and practical examples, this guide should equip you with the knowledge to manage your disk partitions effectively. If you have any specific scenarios or further questions, feel free to ask!