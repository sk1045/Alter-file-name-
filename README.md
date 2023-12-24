import os
import shutil

download_folder = "actual download folder path"  

file_extensions = {
    ".txt": "TextFiles",
    ".pdf": "PDFs",
    ".jpg": "Images",
    ".png": "Images",
    ".docx": "Documents",
    ".xlsx": "Documents",
    ".zip": "Archives",
    ".exe": "Programs",
}

for filename in os.listdir(download_folder):
    file_path = os.path.join(download_folder, filename)


    if os.path.isdir(file_path):
        continue

    _, file_extension = os.path.splitext(filename)

    target_folder = file_extensions.get(file_extension.lower(), "Other")

    target_folder_path = os.path.join(download_folder, target_folder)
    if not os.path.exists(target_folder_path):
        os.mkdir(target_folder_path)

    new_file_path = os.path.join(target_folder_path, filename)
    shutil.move(file_path, new_file_path)

print("Files in the download folder have been organized.")
