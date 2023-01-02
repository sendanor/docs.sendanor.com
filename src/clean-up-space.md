# How to Free Up Disk Space on a Ubuntu Linux System and Docker

As you use your Ubuntu Linux system, you may find that you are running out of
disk space. This can be caused by a variety of factors, such as installing new
programs, downloading large files, or simply using your system over time. In
this tutorial, we will go over several methods that you can use to free up disk
space on your Ubuntu system, as well as how to free up space in Docker if you
are using it. By following these steps, you can reclaim valuable disk space and
improve the performance of your system.

## Freeing Up Disk Space on a Ubuntu Linux System

1. Remove unnecessary files and directories. One of the easiest ways to free up
   disk space on a Ubuntu system is to remove files and directories that you no
   longer need. You can use the `rm` command to delete files and the `rmdir`
   command to delete directories. Make sure to be careful when using these
   commands, as deleted files and directories cannot be recovered.

2. Uninstall unnecessary programs. If you have programs on your system that you
   no longer use, you can uninstall them to free up disk space. To do this, you
   can use the `apt-get` command:
   ```bash
   sudo apt-get remove program_name
   ```

3. Clear the package manager cache. The package manager cache stores the
   packages that you have installed on your system. These packages take up a lot
   of space, and you can free up this space by clearing the cache. To do this,
   you can use the `apt-get autoclean` command:
   ```bash
   sudo apt-get autoclean
   ```

4. Remove old kernels. As you install updates to your system, old kernels are
   kept on your system in case you need to revert to an older version. However,
   these kernels take up a lot of space, and you can remove them to free up disk
   space. To do this, you can use the `apt-get` command:
   ```bash
   sudo apt-get autoremove
   ```

5. Use the `du` command to find large directories. The `du` command allows you
   to see how much space is being used by each directory on your system. You can
   use this command to find large directories and delete the files within them
   to free up space. For example:
   ```bash
   du -h --max-depth=1 /path/to/directory
   ```

6. Use the `df` command to see the available disk space. The `df` command allows
   you to see the amount of available disk space on your system. You can use
   this command to see how much space you have available and how much you have
   used.

7. Remove Snap packages. If you are using Snap packages, you can remove them to
   free up space. To do this, you can use the `snap remove` command:
   ```bash
   snap remove package_name
   ```

8. Clean up the system journal. The `journalctl` utility allows you to view and
   manage the system journal, which stores log data for the system and system
   services. You can use the `journalctl --vacuum-time=3d` command to remove old
   entries from the journal that are older than 3 days and free up disk space.

## Freeing Up Space in Docker

If you are using Docker, there are a few ways you can free up space:

- Remove stopped containers: You can use the `docker rm` command to remove
  stopped containers.

- Remove unused images: You can use the `docker image prune` command to remove
  unused images.

- Remove unused volumes: You can use the `docker volume prune` command to remove
  unused volumes.

- Remove all unused objects: You can use the `docker system prune` command to
  remove all unused objects, including stopped containers, unused images, and
  unused networks.
