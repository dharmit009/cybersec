# Filesystem Hierarchy Standard:

Linux systems store their important files according to a standard layout called the **Filesystem Hierarchy Standard (FHS)**, which has long been maintained by **The Linux Foundation**.

Linux uses the ‘/’ character to separate paths (as sis UNIX unlike Windows, which uses ‘\’) and does not have drive letters. Multiple drives or partitions are mounted as directories in the single filesystem.

Removable media such as USB drives and CDs, and DVDs will show up as mounted at `/run/media/yourusername/disklabel` for recent Linux systems or under `/media` for older distributions.

For example, if your username is *student*, a USB pen drive labeled FEDORA might end up being found at `/run/media/student/FEDORA`, and a file README.txt on that disc would be at `/run/media/student/FEDORA/README.txt`.

All Linux filesystem names are **case-sensitive**, so `/boot`, `/Boot`, and `/BOOT` represent three different directories (or folders). Many distributions distinguish between core utilities needed for proper system operation and other programs, and place the latter in directories under `/usr` (think user). To get a sense for how the other programs are organized, find the `/usr` directory in the diagram from the previous page and compare the subdirectories with those that exist directly under the system root directory (/).
