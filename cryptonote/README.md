This is the reference code for [GrafenoCoin](https://grafenocoin.com) cryptocurrency. Read the Changlogs.txt for more info about the current fork.

### GrafenoCoin is based on the [TurtleCoin](https://github.com/turtlecoin) v0.5.0 code base.

* Official homepage: [GrafenoCoin](http://grafenocoin.com)
* Official repository: [GrafenoCoin GitHub](https://github.com/grafenocoin/grafenocoincoin)
* Official Announcement thread: [GrafenoCoin BitcoinTalk](https://bitcointalk.org/index.php?topic=3086019.0)
* Official Discord: [GrafenoCoin Discord](https://discord.gg/UmZExyz)
* Official Facebook: [GrafenoCoin Facebook](https://www.facebook.com/grafenocoincoin)
* Official Twitter: [GrafenoCoin Twitter](https://twitter.com/gfncoin)
* Official Telegram: [GrafenoCoin Telegram](https://t.me/joinchat/HOvygRE-6UnWOzoh72NVMA)
* Official Whitepaper: [GrafenoCoin Whitepaper](http://grafenocoin.com/whitepaper_grafenocoin.zip)
* Official Block explorer: [GrafenoCoin Block explorer](http://blockexplorer.grafenocoin.com)


## GrafenoCoin Cryptocurrency

GrafenoCoin is an ASIC resistant cryptocurrency designed for mining and perfect for rewarding your workers, co-workers, and colleagues

- Algorithm: CryptoNightLite V1
- Max. supply: 184,467,440,735.0
- CryptoNote name: grafenocoin
- Decimal points: 8
- Block time: 120
- Ticker: GFN
- Emission speed factor: 18
- P2P port: 17239
- RPC port: 18238

## How to compile

### Compile on Linux Ubuntu 16

**1. Install dependencies**

- run an update

``
sudo apt-get update
``

- get all dependencies

``
sudo apt-get install -y build-essential python-dev gcc g++ git cmake librocksdb-dev libboost-all-dev
``

**2. Get the coin**

``
git clone https://github.com/grafenocoin/grafenocoincoin.git grafenocoin
``

**3. CHMOD**

- navigate to:

``
cd grafenocoin/external/rocksdb/build_tools
``

- execute the following commands:

``
chmod +x build_detect_platform
``

``
chmod +x version.sh
``

**4. Build executables**

- Navigate back to repo folder 

``
cd
``

``
cd grafenocoin
``

- prepare the build

``
mkdir build && cd $_
``

``
cmake ..
``

- Export flags

``
export CXXFLAGS="-std=gnu++11"
``

- Make/Build

``
make
``

_Your executables will be located in `build/src` folder._


### Compile on Linux Ubuntu 14

**1. Install dependencies**

- run an update

``
sudo apt-get update
``

- get all dependencies

``
sudo apt-get install -y build-essential python-dev git cmake libboost1.55-all-dev libgflags-dev libsnappy-dev zlib1g-dev libbz2-dev libgflags-dev libgflags2 gcc-4.8 g++-4.8
``

**2. Install RocksDB database (long compilation)**

``
git clone https://github.com/facebook/rocksdb.git
``

``
cd rocksdb
``

``
make all
``

**3. Get the coin**

``
cd
``

``
git clone https://github.com/grafenocoin/grafenocoincoin.git grafenocoin
``

**4. CHMOD**

- navigate to:

``
cd grafenocoin/external/rocksdb/build_tools
``

- execute the following commands:

``
chmod +x build_detect_platform
``

``
chmod +x version.sh
``

**5. Build executables (long compilation)**

- Navigate back to repo folder 

``
cd
``

``
cd grafenocoin
``

- prepare the build

``
mkdir build && cd $_
``

``
cmake ..
``

- Export flags

``
export CXXFLAGS="-std=gnu++11"
``

- Make/Build

``
make
``

### Compile on Windows 7/8/10

**1. Environment**

- Visual Studio 2017 Community Edition with desktop development with C++ and the VC++ v140 toolchain features selected
- Boost 1.59.0, with the installer for MSVC 14

**2. Build**

- From the start menu, open 'x64 Native Tools Command Prompt for vs2017'


``
cd <grafenocoin_directory>
``

``
mkdir build
``

``
cd build
``


-  Set the PATH for Cmake:

``
set PATH="C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\CommonExtensions\Microsoft\CMake\CMake\bin";%PATH%
``

- Run Cmake:

``
cmake -G "Visual Studio 14 Win64" .. -DBOOST_ROOT=C:/local/boost_1_59_0
``

- Build:

``
MSBuild GrafenoCoin.sln /p:Configuration=Release /m
``

_Your binaries  will be located in `..\build\src\Release` folder._


### Credits
Cryptonote Developers, Bytecoin Developers, Monero Developers, Forknote Project, TurtleCoin Developers