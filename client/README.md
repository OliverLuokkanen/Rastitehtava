# Rastitehtava

Tämä repositorio sisältää harjoitustyön rakenteen: server/ (Node.js + Express + MySQL) ja client/ (Qt C++ -asiakas).

Lyhyt kuvaus
- server/: REST-API (CRUD) taululle `car`.
- client/: Qt C++ -asiakasohjelma joka käyttää REST-APIa.

Kansiorakenne (suositus)
- /server
  - app.js
  - package.json
  - .env.example
  - routes/
  - controllers/
  - models/
  - sql/ (esim. create_car_table.sql)
- /client
  - CMakeLists.txt
  - src/ (main.cpp, mainwindow.cpp/.h, restclient.cpp/.h, car*.cpp/.h)
  - README (vaihtoehtoinen)

Ennen ensimmäistä commitia (ohje)
1. Kopioi tämä README.md ja .gitignore juureen.
2. Luo kansiot:
   mkdir server client
3. Siirrä backend-tiedostot server/-kansioon ja Qt-projekti client/-kansioon (esim. mv-komennolla).
4. Lisää, commitoi ja pushaa:
   git add .gitignore README.md server client
   git commit -m "Initial project structure: add server/ and client/ folders"
   git push -u origin main

Serverin käynnistys (esimerkki)
1. Siirry server-kansioon:
   cd server
2. Kopioi .env.example -> .env ja täytä DB-asetukset (älä commitoi .env):
   cp .env.example .env
3. Asenna riippuvuudet:
   npm install
4. Luo tietokanta ja taulu:
   mysql -u root -p < sql/create_car_table.sql
5. Käynnistä:
   npm start

Clientin kääntäminen (Qt6 + CMake)
1. Siirry client-kansioon:
   cd client
2. Luo build-hakemisto ja konfiguroi:
   mkdir build && cd build
   cmake ..
3. Käännä:
   cmake --build .
4. Suorita binääri (esim. ./carclient)

Muistilista
- Älä commitoi node_modules/, .env tai build-kansioita — .gitignore estää tämän.
- Täydennetään README:tä projektin edetessä (esim. API-endpoint-esimerkit ja clientin riippuvuudet).
