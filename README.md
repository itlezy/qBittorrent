qBittorrent - Extensions Mod
------------------------------------------

Branch of v.4.4.x release with some minor improvements

- Low Disk Space Check
- Offline Mode switch with CTRL-F7
- Additional filters for Incomplete and Active with Traffic torrents
- Automatic normal/alternate bandwitdh switch based on download speed
- Move stalled downloads at the bottom of the queue
- Resume torrents on get_peers alerts from the DHT
- Built against latest RC libtorrent 2

Most of this is configurable by editing the `%APPDATA%\qBittorrent\qBittorrent.ini`

Please see the values to set from `preferences.cpp`

```c


int Preferences::getResumeUponGetPeersBehavior() const
{
    // 0 off, 1 standard resume, 2 forced resume
    return value("Extensions/ResumeUponGetPeers/Behavior", 2);
}

int Preferences::getLowDiskSpaceCheckGb() const
{
    return value("Extensions/LowDiskSpaceCheck/Gb", 12);
}

QString Preferences::getLowDiskSpaceCheckPathToMonitor() const
{
    return value<QString>("Extensions/LowDiskSpaceCheck/PathToMonitor");
}

int Preferences::getLowDiskSpaceCheckUpSpeed() const
{
    return value("Extensions/LowDiskSpaceCheck/UpSpeed", 1024 * 1024);
}

int Preferences::getLowDiskSpaceCheckDownSpeed() const
{
    return value("Extensions/LowDiskSpaceCheck/DownSpeed", 16 * 1024);
}

bool Preferences::isDynamicBandwidthSwitchEnabled() const
{
    return value("Extensions/ApplyDynamicBandwidthSwitch/Enabled", true);
}

int Preferences::getDynamicBandwidthSwitchLowerThreshold() const
{
    return value("Extensions/DynamicBandwidthSwitch/LowerThreshold", 256 * 1024);
}

int Preferences::getStalledDownloadBehavior() const
{
    // 0 off, 1 pause, 2 forced download
    return value("Extensions/StalledDownload/Behavior", 2);
}

```
