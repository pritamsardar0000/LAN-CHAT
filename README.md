LAN Chat Messenger With Oracle Database Backup

Project summary:
This is an offline LAN messenger for students on the same Wi-Fi/LAN. One computer runs the Java server. Users open the HTML/CSS/JavaScript UI in a browser from computers or mobiles on the LAN. Accounts, password hashes, groups, and chat backup are saved in Oracle Database.

Main features:
1. Works on LAN without internet
2. Browser UI using HTML, CSS, and JavaScript
3. Java WebSocket server
4. Oracle Database backup through JDBC
5. Register/login with clear invalid user and wrong password messages
6. Strong password rule for registration and password change
7. Group chat for all users
8. Private one-to-one chat
9. Student sub groups
10. Online/offline, Away, and Busy status
11. Hide online status
12. Incoming message notification and unread counter
13. Seen/unseen status for private messages
14. Maximum 10 lines per message
15. Select and delete messages
16. Delete full chat backup
17. Local block/unblock user
18. Local mute/unmute chat notifications
19. Profile, logout, change password, and delete account
20. Admin panel for first registered user

Files:
1. ChatServer.java - Java server
2. index.html - UI layout
3. styles.css - UI design
4. app.js - browser-side logic
5. db.properties - Oracle connection settings
6. database.sql - SQL*Plus table/index setup
7. run-server.bat - compile and run helper
8. lib/ - put Oracle JDBC jar here
9. ORACLE_DATABASE_CHECK_GUIDE.txt - database verification commands and troubleshooting

Important Oracle config:
The Java server reads these keys from db.properties:

db.url=jdbc:oracle:thin:@//localhost:1521/ORCL
db.user=lan_chat
db.password=lan123

Change ORCL, lan_chat, and lan123 to match your Oracle setup.

Common Oracle URL examples:
1. Service name ORCL:
   jdbc:oracle:thin:@//localhost:1521/ORCL
2. Oracle XE pluggable database:
   jdbc:oracle:thin:@//localhost:1521/XEPDB1
3. Old Oracle XE SID style:
   jdbc:oracle:thin:@localhost:1521:XE

SQL*Plus setup:
1. Start Oracle Database and listener.
2. Create or choose an Oracle user/schema for this app.
3. Connect in SQL*Plus as that app user.
4. Run:
   @database.sql

Compile:
javac ChatServer.java

Run on Windows:
java -cp ".;lib\*" ChatServer

Easy run option:
Double-click run-server.bat after putting the Oracle JDBC jar inside the lib folder.

Open on server computer:
http://localhost:8001

Open on another LAN device:
http://SERVER_IP:8001

Example:
http://192.168.31.251:8001

Notes:
1. The first registered chat user becomes the admin.
2. Block and mute are saved only in the current browser/device.
3. Browser notification permission must be allowed before desktop notifications appear.
4. File sharing is intentionally not included because it needs upload storage, download security, binary handling, and file history.
5. If javac cannot overwrite old class files, stop the running Java server first.
6. Use ORACLE_DATABASE_CHECK_GUIDE.txt to confirm tables, sequences, triggers, indexes, login, and chat backup are working correctly.
