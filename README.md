# projeto-so-2022-23

## Código fornecido para o projeto de Sistemas Operativos do ano letivo 2022-2023.

### Consultar o [enunciado do projeto](https://github.com/tecnico-so/enunciado-proj-so-2022-23).


The project consists in 2 parts, a filesystem and a message broker.

Filesystem :

  The project aims to develop a filesystem based on the given codebase. The filesystem is thread-safe, meaning it can be accessed by multiple threads simultaneously without encountering concurrency issues.
  Key functions of the filesystem include:
  - File Opening: It allows opening existing files or creating new ones if they don't exist in the filesystem.
  - File Closing: This function enables closing previously opened files, releasing associated resources.
  
  - File Writing: It facilitates writing data to an opened file, allowing insertion or overwriting of information.
  
  - File Reading: It enables reading data from an opened file, facilitating retrieval of stored information.
  
  -  Symbolic Link Creation: It allows creating symbolic links, which are shortcuts to other files within the filesystem.
  
  -  Hard Link Creation: It enables creating hard links, which are direct references to other files , sharing the same physical content.
  
  - File Removal: It permits removing a file from the filesystem, freeing up the occupied space.
  
  - File Copying: It allows copying a file from the current filesystem to the created filesystem, enabling file transfer between the two.
  
The main objective of the project is to implement these functionalities efficiently and securely, ensuring that multiple threads can interact with the filesystem without causing inconsistencies or errors.

Message broker:

The project involves a message broker system where the server (mbroker) handles publishers, subscribers, and managers. Message boxes store data as files in the filesystem. Clients register and manage sessions using named pipes. The server architecture includes a main thread for registration and a pool of worker threads using a producer-consumer queue for efficient request processing. The server initiates a thread pool to handle registration requests received through a producer-consumer queue. The main thread manages the registration named pipe and enqueues registration requests. Threads in the pool wait for new sessions after completing a task. The filesystem manages message storage, while the manager handles box operations and listing. In the project, active waiting is avoided due to the use of signals. This means that there is no need for threads to continuously check for events or wait actively. The server utilizes signals to efficiently handle and respond to various events, ensuring a more streamlined and responsive operation. In addition to the previous features, an added functionality is implemented in the project. When a manager creates a box, they have the option to assign a password to that specific box. This password is then required to perform read, write, and removal operations on the box.


