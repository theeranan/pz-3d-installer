# Project Zomboid 3D Installer (pz3d / Viewpoint)

ตัวติดตั้ง ZombieBuddy สำหรับม็อด 3D ของ Project Zomboid Build 42 ทั้ง **pz3d** และ **Project Viewpoint**
A one-click ZombieBuddy setup for the Project Zomboid Build 42 3D mods **pz3d** and **Project Viewpoint**.

pz3d and Viewpoint are Java mods. They only run once ZombieBuddy is installed into the game folder, and subscribing to ZombieBuddy on the Workshop doesn't do that by itself. This installer does it, then lets you raise the game's memory limit. The default 3 GB is too small for 3D with many mods and shows as stutter.

## ดาวน์โหลด / Download

**[ZombieBuddy-3D-Installer.zip](https://github.com/theeranan/pz-3d-installer/releases/latest/download/ZombieBuddy-3D-Installer.zip)** ใช้ได้ทั้ง pz3d และ Viewpoint / works for both pz3d and Viewpoint

ใช้ม็อด 3D ทีละตัว อย่าเปิด pz3d กับ Viewpoint พร้อมกัน / Use one 3D mod at a time; don't enable pz3d and Viewpoint together.

## วิธีติดตั้ง / How to install

1. Subscribe ใน Steam Workshop / Subscribe on the Steam Workshop:
   - [ZombieBuddy](https://steamcommunity.com/sharedfiles/filedetails/?id=3619862853)
   - [pz3d](https://steamcommunity.com/sharedfiles/filedetails/?id=3807334881) **หรือ / or** [Project Viewpoint](https://steamcommunity.com/sharedfiles/filedetails/?id=3809306528)

   รอ Steam ดาวน์โหลดเสร็จ / Wait for Steam to finish downloading.
2. ปิดเกม / Close the game.
3. แตกไฟล์ zip แล้วดับเบิลคลิก **Install.bat** / Extract the zip and double-click **Install.bat**.
4. กด **1** แล้ว **y** / Press **1**, then **y**.
5. เลือก RAM ของเกม (กด Enter = ค่าแนะนำ) แล้ว **y** / Pick the game's memory limit (Enter = recommended), then **y**.
6. เข้าเกม แล้วเปิดม็อด 3D ในรายการม็อด / Start the game and enable the 3D mod in the mod list.

## มันทำอะไรบ้าง / What it changes

ก่อนทำอะไรจะแสดงรายการให้ยืนยันทุกครั้ง / Every change is listed and confirmed first:

- ก๊อป `ZombieBuddy.jar` และ `zbNative.dll` จากไอเทม ZombieBuddy ที่ subscribe ไว้ ลงโฟลเดอร์เกม ไม่มีการดาวน์โหลดอะไรเพิ่ม ถ้ามี `ZombieBuddy.jar` อื่นอยู่แล้ว จะเก็บไว้เป็น `ZombieBuddy.jar.orig`
  Copies `ZombieBuddy.jar` and `zbNative.dll` from the subscribed ZombieBuddy item into the game folder. Nothing is downloaded. A different existing `ZombieBuddy.jar` is kept as `ZombieBuddy.jar.orig`.
- เพิ่ม `-agentlib:zbNative` ใน `ProjectZomboid64.json` และ `ProjectZomboid64.bat` เหมือนตัวติดตั้งของ ZombieBuddy เอง
  Adds `-agentlib:zbNative` to `ProjectZomboid64.json` and `ProjectZomboid64.bat`, the same way ZombieBuddy's own installer does.
- ตั้ง RAM (`-Xmx`) ในสองไฟล์เดียวกันนี้ / Sets the memory limit (`-Xmx`) in the same two files.

ไม่แตะ Steam launch options / Steam launch options are not touched.

## รู้ไว้ / Notes

- รันใหม่หลัง ZombieBuddy อัปเดต และหลัง Steam ตรวจสอบหรืออัปเดตเกม (Steam จะคืนไฟล์เดิมและ RAM 3 GB)
  Run it again after a ZombieBuddy update, and after Steam verifies or updates the game (Steam puts the original files and the 3 GB limit back).
- ถอนการติดตั้ง: รันอีกครั้งแล้วกด **2** เอา ZombieBuddy ออกทั้งหมดและคืน RAM เป็น 3 GB / To uninstall, run it again and press **2**: removes everything ZombieBuddy added and puts the memory limit back to 3 GB.
- ตอนเข้าเกมครั้งแรก ZombieBuddy จะถามว่าจะให้โหลด Java mod ไหม ให้กด Allow
  On first start, ZombieBuddy asks whether to load the Java mod. Choose Allow.
- สคริปต์เป็นไฟล์ข้อความ เปิดอ่านได้ว่าทำอะไร / The script is plain text; read it to see exactly what it does.

Credits: [ZombieBuddy](https://github.com/zed-0xff/ZombieBuddy) by zed-0xff, pz3d by kolpaque, Project Viewpoint by its author. This installer only sets them up.
