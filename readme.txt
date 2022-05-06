Vampire: The Masquerade - Bloodlines (Wine wrapper) - Release: 2021/07/11
PLEASE NOTE: THIS IS COMPLETELY UNOFFICIAL AND UNSUPPORTED BY GOG OR ACTIVISION. Use at your own risk etc. etc. ***

If any help is needed, use GOG's forums:

	https://www.gog.com/forum/vampire_the_masquerade_series/vampire_the_masquerade_bloodlines_for_linux
	https://www.gog.com/forum/general/adamhms_linux_wine_wrappers_news_faq_discussion
	https://www.gog.com/forum/general/the_judas_does_this_run_in_wine_thread_v1173

******************************

There should be 3 files in this archive:

readme.txt
vtmb_res.tar.xz
vtmb_wine.sh

This will create a Wine-wrapped version of Vampire: The Masquerade - Bloodlines using the GOG release of the game. To use it, run the vtmb_wine.sh script and specify the path to the installer files with the -respath="<path>" argument. If the installer files cannot be found in the specified path (or if no path is specified) then it will look for them in the current directory, then the build path, and then the directory containing the script.

By default the wrapper will be created in the same directory as the script is started in, but you can also specify a different directory with the -buildpath="<path>" argument. Alternatively, both the resource path and build path can be set using the environment variables WINEWRAP_RESPATH and WINEWRAP_BUILDPATH respectively.

These are the GOG installer files that are expected:

setup_vampire_the_masquerade_-_bloodlines_1.2_(up_10.2)_(28160)-1.bin
setup_vampire_the_masquerade_-_bloodlines_1.2_(up_10.2)_(28160).exe

If the installer has been replaced with a new version but the wrapper has not yet been updated for it you can try using the wrapper script with the new installer by using the -planb option. The installer can be specified with -planb="</path/to/installer/installer.exe"> or if you leave it blank you will be prompted to select it via a Zenity file selection window. The script will then try to build the wrapper by running the installer rather than extracting it - just click through the installer and let it install; do not change the default install path or it will fail. Please note that any patches or DLC that would otherwise be installed will need to be installed separately via the wrapper's start script, and building wrappers this way takes a *lot* longer (and may not work depending on what has changed with the new installer), so using this option is not recommended under normal circumstances.

You will also need to have the following packages installed for everything to work correctly (assuming Linux Mint, Ubuntu, or another Ubuntu-based distro; on other distros the package names may differ and/or other packages may also be required, such as unrar, cabextract, zenity, libsdl2 etc.): icoutils, unrar, zenity, Wine's dependencies. An easy way to get the dependencies on Linux Mint 19.x is to use my common dependencies meta-package, which can be found here: https://www.gog.com/forum/general/adamhms_linux_mint_beginners_guide

When it has finished there will be a directory in the build path named "VTM - Bloodlines" containing the game set up within a preconfigured Wine prefix, plus Wine and a start script. Simply run the start.sh script to play (the script also includes the option to create a shortcut - see the release notes for more info). The game EULA, manual, release notes and other information can be found in the docs directory in the assembled game package.

To uninstall simply delete the game directory and any shortcuts you created (and the user data directory in ~/.local/share if you don't want to keep your saves & settings).

If you want to make a backup of the assembled package for easier installs in future then it's recommended to do so before running it for the first time, so that certain links, user directories & other clutter is kept out. If you run the build script with -xz or -gz arguments a tarball will also be produced (xzip/gzip compressed respectively - xz will take much longer but produce a much smaller file) so that a "clean" copy can be kept for archival & future use.

The wrapper uses the Wine 5.0 package provided by PlayOnLinux, which the script will attempt to download automatically along with Winetricks if they have not previously been downloaded already by one of my wrapper scripts - these will be downloaded to ~/.cache/winewrap

For more information about Wine, Proton, PlayOnLinux and Lutris, see:
https://www.winehq.org
https://www.wine-staging.com
https://github.com/ValveSoftware/Proton
https://www.playonlinux.com
https://lutris.net
http://winetricks.org

Check out my other Wine wrappers for GOG games: https://www.gog.com/forum/general/adamhms_linux_wine_wrappers_news_faq_discussion
