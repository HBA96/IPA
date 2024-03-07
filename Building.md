# Method 1: Github action
## Requirement:
- A Github account.
- A decrypted YouTube ipa. You must upload it to a cloud storage service (I strongly recommend you to use https://litterbox.catbox.moe, some cloud storage services won't work as they don't allow direct download.)

## Step:
1. Fork this repository.
2. In your forked repository, go to the **Actions** tab > Select **Build and Release YTLitePlus** > **Run workflow** > Enter the direct link to the IPA.

![Screenshot · Balackburn_YTLitePlus](https://github.com/Balackburn/YTLitePlus/assets/93828569/fe29e1ec-5d4d-4771-bc64-1964d6468fc9)

3. It will take a while. You will see the IPA in the **Releases tab** of your repository.
4. After downloading the .ipa, we recommend you delete the release to avoid any problems with Google, as the .ipa file is not your proprety and isn't authorized for distribution.

***

# Method 2: theos-jailed

## Note 
This method has never worked for me but it may be my computer, please let me know in the discussions if you have successfully built the .ipa with build.sh

## Requirement:
- Xcode 13+ & Xcode Command Line Tools
- theos & theos-jailed
- A patched iOS 16.5 SDK (with Private Frameworks) in `theos/sdks`: https://github.com/theos/sdks

## Step:
1. Clone this repo: `git clone --recursive https://github.com/Balackburn/YTLitePlus.git`
2. Change the working directoy: `cd ./YTLitePlus`
3. _Optional: Updates submodules_ `git submodule update --remote --merge`
4. Make the `build.sh` script executable: `chmod +x ./build.sh`
5. _Optional: open `Makefile` and add or remove any tweaks you want. You can also edit the bundle ID / display name of the app. I highly recommend you take a look at the theos-jailed [wiki](https://github.com/kabiroberai/theos-jailed/wiki/Usage)._
6. Run the buildapp script: `./build.sh`, provide the decrypted YouTube IPA when asked.

```
$ git clone --recursive https://github.com/qnblackcat/YTLitePlus.git
$ cd ./YTLitePlus 
$ git submodule update --remote --merge
$ chmod +x ./build.sh
$ ./build.sh
```
Or in one command
```
git clone --recursive https://github.com/Balackburn/YTLitePlus.git && cd ./YTLitePlus && git submodule update --remote --merge && chmod +x ./build.sh && ./build.sh
```
![Screen Shot 2](https://user-images.githubusercontent.com/52943116/168122339-cfa388cb-4956-48cc-a4d5-cfba22612bbf.png)

✔︎ That's it! Grab a coffee ☕️ It will take a while. The IPA is stored in `./YTLitePlus/packages`

Thank to [@qnblackhat](https://github.com/qnblackcat/uYouPlus) for the [build.sh](https://raw.githubusercontent.com/qnblackcat/uYouPlus/main/build.sh) and this [Building Wiki](https://github.com/qnblackcat/uYouPlus/wiki/Building) and for a lot of YTLitePlus code forked from uYouPlus.