$engine: 3
$onesync: on
name: QBCore Framework
version: 2.2.4
author: JericoFx & Kakarot & Hamy
description: An advanced FiveM RP framework including jobs, gangs, housing & more!

tasks:
  #  Download Base Files
  - action: download_github
    src: https://github.com/qbcore-framework/txAdminRecipe
    ref: main
    dest: ./tmp/qbcore

  - action: move_path
    src: ./tmp/qbcore/server.cfg
    dest: ./server.cfg

  - action: move_path
    src: ./tmp/qbcore/myLogo.png
    dest: ./myLogo.png

  # Prepare Database
  - action: connect_database
  - action: query_database
    file: ./tmp/qbcore/qbcore.sql


  # STANDALONE
  - action: download_github
    src: https://github.com/citizenfx/cfx-server-data
    subpath: resources
    dest: ./resources/[cfx-default]

  - action: download_file
    path: ./tmp/files/oxmysql.zip
    url: https://github.com/overextended/oxmysql/releases/download/v2.6.0/oxmysql.zip
  - action: unzip
    dest: ./resources/[standalone]
    src: ./tmp/files/oxmysql.zip

  - action: download_file
    path: ./tmp/menuv.zip
    url: https://github.com/ThymonA/menuv/releases/download/v1.4.1/menuv_v1.4.1.zip
  - action: unzip
    dest: ./resources/[standalone]/menuv
    src: ./tmp/menuv.zip

  - action: download_github
    dest: ./resources/[standalone]/bob74_ipl
    ref: master
    src: https://github.com/qbcore-framework/bob74_ipl

  - action: download_github
    dest: ./resources/[standalone]/safecracker
    ref: main
    src: https://github.com/qbcore-framework/safecracker

  - action: download_github
    dest: ./resources/[standalone]/screenshot-basic
    ref: master
    src: https://github.com/citizenfx/screenshot-basic

  - action: download_github
    dest: ./resources/[standalone]/progressbar
    ref: main
    src: https://github.com/qbcore-framework/progressbar

  - action: download_github
    dest: ./resources/[standalone]/interact-sound
    ref: master
    src: https://github.com/qbcore-framework/interact-sound

  - action: download_github
    dest: ./resources/[standalone]/mhacking
    ref: main
    src: https://github.com/qbcore-framework/mhacking

  - action: download_github
    dest: ./resources/[standalone]/connectqueue
    ref: master
    src: https://github.com/qbcore-framework/connectqueue

  - action: download_github
    dest: ./resources/[standalone]/rpemotes
    ref: master
    src: https://github.com/qbcore-framework/rpemotes

  - action: download_github
    dest: ./resources/[standalone]/PolyZone
    ref: master
    src: https://github.com/qbcore-framework/PolyZone

  - action: download_github
    dest: ./resources/[standalone]/LegacyFuel
    ref: master
    src: https://github.com/qbcore-framework/LegacyFuel

- action: replace_string
    mode: all_vars
    file: 
      - ./resources/[standalone]/ghmattimysql/config.json

    # VOICE
  - action: download_github
    dest: ./resources/[voice]/pma-voice
    ref: main
    src: https://github.com/AvarianKnight/pma-voice

  - action: download_github
    dest: ./resources/[voice]/qb-radio
    ref: main
    src: https://github.com/qbcore-framework/qb-radio

    # MAPS
  - action: download_github
    dest: ./resources/[defaultmaps]/hospital_map
    ref: main
    src: https://github.com/qbcore-framework/hospital_map

  - action: download_github
    dest: ./resources/[defaultmaps]/dealer_map
    ref: main
    src: https://github.com/qbcore-framework/dealer_map

  - action: download_github
    dest: ./resources/[defaultmaps]/[prison_map]
    ref: main
    src: https://github.com/qbcore-framework/prison_map

  # Downloading QBCore resources
  - action: download_github
    dest: ./resources/[qb]/qb-core
    ref: main
    src: https://github.com/qbcore-framework/qb-core

  - action: download_github
    dest: ./resources/[qb]/qb-scoreboard
    ref: main
    src: https://github.com/qbcore-framework/qb-scoreboard

  - action: download_github
    dest: ./resources/[qb]/qb-adminmenu
    ref: main
    src: https://github.com/qbcore-framework/qb-adminmenu

  - action: download_github
    dest: ./resources/[qb]/qb-multicharacter
    ref: main
    src: https://github.com/qbcore-framework/qb-multicharacter

  - action: download_github
    dest: ./resources/[qb]/qb-target
    ref: main
    src: https://github.com/qbcore-framework/qb-target

  - action: waste_time # prevent github throttling
    seconds: 10

  - action: download_github
    dest: ./resources/[qb]/qb-vehiclesales
    ref: main
    src: https://github.com/qbcore-framework/qb-vehiclesales

  - action: download_github
    dest: ./resources/[qb]/qb-vehicleshop
    ref: main
    src: https://github.com/qbcore-framework/qb-vehicleshop

  - action: download_github
    dest: ./resources/[qb]/qb-houserobbery
    ref: main
    src: https://github.com/qbcore-framework/qb-houserobbery

  - action: download_github
    dest: ./resources/[qb]/qb-prison
    ref: main
    src: https://github.com/qbcore-framework/qb-prison

  - action: download_github
    dest: ./resources/[qb]/qb-atms
    ref: main
    src: https://github.com/qbcore-framework/qb-atms

  - action: download_github
    dest: ./resources/[qb]/qb-hud
    ref: main
    src: https://github.com/qbcore-framework/qb-hud

  - action: download_github
    dest: ./resources/[qb]/qb-management
    ref: main
    src: https://github.com/qbcore-framework/qb-management

  - action: download_github
    dest: ./resources/[qb]/qb-weed
    ref: main
    src: https://github.com/qbcore-framework/qb-weed

  - action: download_github
    dest: ./resources/[qb]/qb-lapraces
    ref: main
    src: https://github.com/qbcore-framework/qb-lapraces

  - action: download_github
    dest: ./resources/[qb]/qb-inventory
    ref: main
    src: https://github.com/qbcore-framework/qb-inventory

  - action: download_github
    dest: ./resources/[qb]/qb-houses
    ref: main
    src: https://github.com/qbcore-framework/qb-houses

  - action: download_github
    dest: ./resources/[qb]/qb-garages
    ref: main
    src: https://github.com/qbcore-framework/qb-garages

  - action: download_github
    dest: ./resources/[qb]/qb-ambulancejob
    ref: main
    src: https://github.com/qbcore-framework/qb-ambulancejob

  - action: download_github
    dest: ./resources/[qb]/qb-vehiclefailure
    ref: main
    src: https://github.com/qbcore-framework/qb-vehiclefailure

  - action: waste_time # prevent github throttling
    seconds: 10

  - action: download_github
    dest: ./resources/[qb]/qb-radialmenu
    ref: main
    src: https://github.com/qbcore-framework/qb-radialmenu

  - action: download_github
    dest: ./resources/[qb]/qb-crypto
    ref: main
    src: https://github.com/qbcore-framework/qb-crypto

  - action: download_github
    dest: ./resources/[qb]/qb-weathersync
    ref: main
    src: https://github.com/qbcore-framework/qb-weathersync

  - action: download_github
    dest: ./resources/[qb]/qb-policejob
    ref: main
    src: https://github.com/qbcore-framework/qb-policejob

  - action: download_github
    dest: ./resources/[qb]/qb-traphouse
    ref: main
    src: https://github.com/qbcore-framework/qb-traphouse

  - action: download_github
    dest: ./resources/[qb]/qb-apartments
    ref: main
    src: https://github.com/qbcore-framework/qb-apartments

  - action: download_github
    dest: ./resources/[qb]/qb-vehiclekeys
    ref: main
    src: https://github.com/qbcore-framework/qb-vehiclekeys

  - action: download_github
    dest: ./resources/[qb]/qb-mechanicjob
    ref: main
    src: https://github.com/qbcore-framework/qb-mechanicjob

  - action: download_github
    dest: ./resources/[qb]/qb-phone
    ref: main
    src: https://github.com/qbcore-framework/qb-phone

  - action: download_github
    dest: ./resources/[qb]/qb-vineyard
    ref: main
    src: https://github.com/qbcore-framework/qb-vineyard

  - action: download_github
    dest: ./resources/[qb]/qb-weapons
    ref: main
    src: https://github.com/qbcore-framework/qb-weapons

  - action: download_github
    dest: ./resources/[qb]/qb-scrapyard
    ref: main
    src: https://github.com/qbcore-framework/qb-scrapyard

  - action: download_github
    dest: ./resources/[qb]/qb-tunerchip
    ref: main
    src: https://github.com/qbcore-framework/qb-tunerchip

  - action: download_github
    dest: ./resources/[qb]/qb-towjob
    ref: main
    src: https://github.com/qbcore-framework/qb-towjob

  - action: download_github
    dest: ./resources/[qb]/qb-streetraces
    ref: main
    src: https://github.com/qbcore-framework/qb-streetraces

  - action: download_github
    dest: ./resources/[qb]/qb-storerobbery
    ref: main
    src: https://github.com/qbcore-framework/qb-storerobbery

  - action: download_github
    dest: ./resources/[qb]/qb-spawn
    ref: main
    src: https://github.com/qbcore-framework/qb-spawn

  - action: download_github
    dest: ./resources/[qb]/qb-skillbar
    ref: main
    src: https://github.com/qbcore-framework/qb-skillbar

  - action: download_github
    dest: ./resources/[qb]/qb-smallresources
    ref: main
    src: https://github.com/qbcore-framework/qb-smallresources

  - action: download_github
    dest: ./resources/[qb]/qb-recyclejob
    ref: main
    src: https://github.com/qbcore-framework/qb-recyclejob

  - action: download_github
    dest: ./resources/[qb]/qb-diving
    ref: main
    src: https://github.com/qbcore-framework/qb-diving

  - action: download_github
    dest: ./resources/[qb]/qb-cityhall
    ref: main
    src: https://github.com/qbcore-framework/qb-cityhall

  - action: download_github
    dest: ./resources/[qb]/qb-truckrobbery
    ref: main
    src: https://github.com/qbcore-framework/qb-truckrobbery

  - action: download_github
    dest: ./resources/[qb]/qb-pawnshop
    ref: main
    src: https://github.com/qbcore-framework/qb-pawnshop

  - action: download_github
    dest: ./resources/[qb]/qb-taxijob
    ref: main
    src: https://github.com/qbcore-framework/qb-taxijob

  - action: download_github
    dest: ./resources/[qb]/qb-busjob
    ref: main
    src: https://github.com/qbcore-framework/qb-busjob

  - action: download_github
    dest: ./resources/[qb]/qb-newsjob
    ref: main
    src: https://github.com/qbcore-framework/qb-newsjob

  - action: download_github
    dest: ./resources/[qb]/qb-jewelery
    ref: main
    src: https://github.com/qbcore-framework/qb-jewelery

  - action: waste_time # prevent github throttling
    seconds: 10

  - action: download_github
    dest: ./resources/[qb]/qb-bankrobbery
    ref: main
    src: https://github.com/qbcore-framework/qb-bankrobbery

  - action: download_github
    dest: ./resources/[qb]/qb-truckerjob
    ref: main
    src: https://github.com/qbcore-framework/qb-truckerjob

  - action: download_github
    dest: ./resources/[qb]/qb-keyminigame
    ref: main
    src: https://github.com/qbcore-framework/qb-keyminigame

  - action: download_github
    dest: ./resources/[qb]/qb-fitbit
    ref: main
    src: https://github.com/qbcore-framework/qb-fitbit

  - action: download_github
    dest: ./resources/[qb]/qb-commandbinding
    ref: main
    src: https://github.com/qbcore-framework/qb-commandbinding

  - action: download_github
    dest: ./resources/[qb]/qb-banking
    ref: main
    src: https://github.com/qbcore-framework/qb-banking

  - action: download_github
    dest: ./resources/[qb]/qb-clothing
    ref: main
    src: https://github.com/qbcore-framework/qb-clothing

  - action: download_github
    dest: ./resources/[qb]/qb-hotdogjob
    ref: main
    src: https://github.com/qbcore-framework/qb-hotdogjob

  - action: download_github
    dest: ./resources/[qb]/qb-doorlock
    ref: main
    src: https://github.com/qbcore-framework/qb-doorlock

  - action: download_github
    dest: ./resources/[qb]/qb-garbagejob
    ref: main
    src: https://github.com/qbcore-framework/qb-garbagejob

  - action: download_github
    dest: ./resources/[qb]/qb-drugs
    ref: main
    src: https://github.com/qbcore-framework/qb-drugs

  - action: download_github
    dest: ./resources/[qb]/qb-shops
    ref: main
    src: https://github.com/qbcore-framework/qb-shops

  - action: download_github
    dest: ./resources/[qb]/qb-lockpick
    ref: main
    src: https://github.com/qbcore-framework/qb-lockpick

  - action: download_github
    dest: ./resources/[qb]/qb-interior
    ref: main
    src: https://github.com/qbcore-framework/qb-interior

  - action: download_github
    dest: ./resources/[qb]/qb-menu
    ref: main
    src: https://github.com/qbcore-framework/qb-menu

  - action: download_github
    dest: ./resources/[qb]/qb-input
    ref: main
    src: https://github.com/qbcore-framework/qb-input

  - action: download_github
    dest: ./resources/[qb]/qb-loading
    ref: main
    src: https://github.com/qbcore-framework/qb-loading

  # Clean up
  - action: remove_path
    path: ./tmp
