# FileSync3: Distributed File System

FileSync3 is a distributed file system that enables seamless file management between a client and three servers (Smain, Spdf, and Stext). The system supports multiple client connections, allowing users to upload, download, and manage files across different servers. While clients interact only with the Smain server, Smain handles the distribution of files to the appropriate servers in the background.

## Features

- **Upload Files**: Clients can upload `.c`, `.pdf`, and `.txt` files to the Smain server.
- **Download Files**: Clients can download files from Smain.
- **Remove Files**: Clients can delete files stored on Smain and retrieve them to their local directory.
- **Create Tar Files**: Clients can create a tar archive of specific file types and download it from Smain.
- **Path Display**: Clients can display the full path of a file.

## Server Distribution

- `.c` files are stored locally on Smain.
- `.pdf` files are transferred to the Spdf server.
- `.txt` files are transferred to the Stext server.

## Getting Started

### Prerequisites

- C Compiler (GCC recommended)
- Basic knowledge of socket programming in C

### Installation

1. **Clone the Repository**
   ```bash
   git clone https://github.com/JaniNaiya/personal-portfolio-website.git
   cd personal-portfolio-website
   
2. **Compile the Servers and Client:**
   ```bash
   gcc -o smain Smain.c
   gcc -o spdf Spdf.c
   gcc -o stext Stext.c
   gcc -o client client.c
   
3. **Run the Servers: Run each server on a separate terminal:**
   ```bash
   ./Smain
   ./Spdf
   ./Stext
   
4. **Run the Client:**
   ```bash
   ./client24s

## Usage

Use the following client commands to interact with the servers:

- **`ufile filename destination_path`**: Uploads a file to the Smain server.
- 
  *Example:*
  
  ```bash
  client24s$ ufile sample.c ~smain/folder1/folder2
  
Transfers sample.c to the specified folder on the Smain server. 

- **`dfile filename`**: Downloads a file from the Smain server.
   *Example:*
  
  ```bash
  client24s$ dfile ~smain/folder1/folder2/sample.c

Retrieves sample.c from the Smain server to the client's current working directory.

- **`rmfile filename`**: Removes a file from the server.
   *Example:*
  
  ```bash
  client24s$ rmfile ~smain/folder1/folder2/sample.pdf
Requests Spdf to delete sample.pdf in the corresponding directory.

- **`dtar filetype`**:  Creates and downloads a tar file of the specified file type.
   *Example:*
  
  ```bash
  client24s$ dtar .c
Creates cfiles.tar containing all .c files from ~/smain and sends it to the client.

- **`display pathname`**:  Displays all files in the specified path.
   *Example:*
  
  ```bash
  client24s$ display ~smain/folder1
Lists .c, .pdf, and .txt files from the specified directory.
   
## Error Handling

- The program includes error handling to manage invalid commands, network errors, and file operations.
- Error messages provide feedback to the user for corrective actions.
  
## License

-This project is licensed under the MIT License - see the LICENSE file for details.     
  ```bash
  You can copy this entire content into a `README.md` file and add it to your GitHub repository. This will ensure a professional and well-structured presentation of your project.
