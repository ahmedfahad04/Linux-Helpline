### Concrete, minimal steps to Add Standalone Desktop Entry - works for **any app like `Zotero`**

---

## 1️⃣ Put the app in a fixed location

```bash
sudo mkdir -p /opt
sudo mv <EXTRACTED_APP_FOLDER> /opt/<appname>
```

Example:

```bash
sudo mv Zotero_linux-x86_64 /opt/zotero
```

Executable must be:

```
/opt/zotero/zotero
```

Test:

```bash
/opt/zotero/zotero
```

---

## 2️⃣ Create the desktop entry

```bash
sudo nano /usr/share/applications/zotero.desktop # or .local/share/applications/zotero.desktop
```

Paste:

```ini
[Desktop Entry]
Name=Zotero
Exec=/opt/zotero/zotero
Icon=/opt/zotero/chrome/icons/default/default128.png # put the icon location
Type=Application
Terminal=false
Categories=Office;Education;
```

Save and exit.

---

## 3️⃣ Make it executable

```bash
sudo chmod +x /usr/share/applications/zotero.desktop # or .local/share/applications/zotero.desktop
```

---

## 4️⃣ Refresh app menu

```bash
sudo update-desktop-database
```

---

## 5️⃣ Log out → log in

---

## 6️⃣ Launch

* Press **Super / Windows key**
* Type **Zotero**
* Click to open

---

### That’s it.

This is the **canonical, distro-safe, desktop-environment-safe** method.
