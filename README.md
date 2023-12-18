# Alter-file-name-
import os

def rename_files(folder_path, new_name):
    for filename in os.listdir(folder_path):
        # Construct the full file path
        file_path = os.path.join(folder_path, filename)

        # Check if it's a file (not a directory)
        if os.path.isfile(file_path):
            new_file_name = f'{prefix}{filename}'
            new_file_path = os.path.join(folder_path, new_file_name)
            os.rename(file_path, new_file_path)
            print(f'Renamed: {filename} -> {new_file_name}')
folder_path = 'output pathr'
new_name = 'new_prefix_'
rename_files(folder_path, prefix)
