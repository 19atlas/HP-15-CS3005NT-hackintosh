# HP-15-CS3005NT-hackintosh
EFI folder for HP 15-CS3005NT 
![2023-02-09_09-58](https://user-images.githubusercontent.com/67108558/217780432-23ce435f-5c53-4f1d-ad1e-ff8d7f16dd4b.png)

## My Laptop
| Specs         | Details                    
| -----------   | ------------------------------- |
| Laptop        | `HP Pavilion laptop 15-CS3005NT`|
| CPU           | `Intel Core i5-1035G1`          |
| IGPU          | `0x8A520000 Intel UHD Graphics` |
| dGPU (Disable)| `Nvidia MX130`                  |
| Bios Name     | `\_SB.PCI0.GFX0`                |
| RAM           | `8 GB DDR4 SDRAM`               |
| OpenCore ver. | `V0.7.5`                        |
| HP BIOS ver.  | `F.15`                          |

### Works
- [x] Intel Integrated Graphics (IGPU)
- [x] USB
- [x] Webcam
- [x] Brightness controls
- [x] TouchPad
- [x] Speakers
- [x] Integrated Microphone (you can talk to Siri)
- [x] Apple Services (iCloud, Apple Music, Apple TV ...)

### Doesn't work
- [ ] SD Card Reader (haven't tested)
- [ ] Airdrop (haven't tested)
- [ ] Sleep
- [ ] TouchPad with Advanced Gestures
- [ ] Battery percentage
- [ ] Bluetooth

### BIOS Setup
- Disable "Secure Boot"
- Disable VT-d (can be enabled if you set `DisableIoMapper` to YES)
- Disable Intel SGX
- Disable Intel Platform Trust

### Config reminders for HP
- Kernel > Quirks > LapicKernelPanic -> true
- UEFI > Quirks > UnblockFsConnect -> true

### IGPU fixup for G1
```xml
			<key>PciRoot(0x0)/Pci(0x2,0x0)</key>
			<dict>
				<key>AAPL,GfxYTile</key>
				<data>AQAAAA==</data>
				<key>AAPL,ig-platform-id</key>
				<data>AABSig==</data>
				<key>device-id</key>
				<data>UooAAA==</data>
				<key>device_type</key>
				<string>VGA compatible controller</string>
				<key>enable-hdmi-dividers-fix</key>
				<data>AQAAAA==</data>
				<key>enable-hdmi20</key>
				<data>AQAAAA==</data>
				<key>enable-lspcon-support</key>
				<data>AQAAAA==</data>
				<key>framebuffer-con1-enable</key>
				<data>AQAAAA==</data>
				<key>framebuffer-con1-pipe</key>
				<data>EgAAAA==</data>
				<key>framebuffer-con1-type</key>
				<data>AAgAAA==</data>
				<key>framebuffer-fbmem</key>
				<data>AACQAA==</data>
				<key>framebuffer-patch-enable</key>
				<data>AQAAAA==</data>
				<key>framebuffer-stolenmem</key>
				<data>AAAwAQ==</data>
				<key>framebuffer-unifiedmem</key>
				<data>AAAAgA==</data>
				<key>model</key>
				<string>Intel Iris Plus Graphics G7</string>
			</dict>
```

### Teşekkürler (Thanks)
- yusfklncc (https://osxinfo.net/uye/yusfklncc.7802/)
- topic (https://osxinfo.net/konu/macos-monterey-intel-ve-amd-kurulum-imaji.24330/)
