# SOCKETIO

model.js


const fs = require("fs")
const path = require("path")
const dbpath = path.join(__dirname, "../db/mensajes.sqlite")
const sqlite = require("better-sqlite3")
const db = new sqlite(dbpath)

function initDB(){
    const init = fs.readFileSync(path.join(__dirname, "../db/init.sql"), "utf8")
    const statements = init.split(";").filter( statement => statement.trim() !== "")
    statements.forEach(statement => {
        db.prepare(statement).run()
        //const row = db.prepare('SELECT * FROM mensajes').all();
        //console.log(row)
    })
}

function read(){
    const statement = db.prepare("SELECT * FROM mensajes ORDER BY id DESC LIMIT 5 ").all()
    console.log(statement)
}

initDB();
read();

init.sql

DROP TABLE IF EXISTS mensajes;
CREATE TABLE mensajes (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    mensaje TEXT NOT NULL
);
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo15');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo14');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo13');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo12');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo11');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo10');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo9');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo8');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo7');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo6');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo4');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo3');
INSERT INTO mensajes (mensaje) VALUES ('hola mundo2');
