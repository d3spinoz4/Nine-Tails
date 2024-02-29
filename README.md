# Fedora 39 Real Time Kernel (6.7.3-100)

`sudo rpm -ivh kernel-6.7.3-100.fc39.aarch64.rpm kernel-core-6.7.3-100.fc39.aarch64.rpm kernel-modules-core-6.7.3-100.fc39.aarch64.rpm kernel-modules-6.7.3-100.fc39.aarch64.rpm`

The name was not changed to `kernel-rt` but can be verified by running:

`uname -a`

You should get a similar response to:

`Linux host 6.7.3-100.fc39.aarch64 #1 SMP PREEMPT_DYNAMIC Sat Feb 17 23:13:21 EST 2024 aarch64 GNU/Linux`

Finally you may add the following kernel parameter to `/etc/default/grub` in the `GRUB_CMDLINE_LINUX="rhgb quiet"` section:

`preempt=full`

Then run the following command to update grub and reboot, you can configure grub for which entry to load or you may choose the kernel during boot if it's not newer than the one you had installed before:

`grub2-mkconfig -o /etc/grub2-efi.cfg`

Or

You could just install Fedora 39 and add the kernel parameter as it ships by default with `PREEMPT_DYNAMIC`
