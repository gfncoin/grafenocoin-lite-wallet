# GrafenoCoin lite wallet

_This is the reference code for lite GUI wallet for the [GrafenoCoin](https://grafenocoin.com) cryptocurrency._

## Features

- CPU miner
- Remote node sync
- No local blockchain storage
- Send GFN
- Receive GFN
- Address book
- CSV export
- Transactions history
- Create wallet
- Open wallet
- Backup wallet
- Import keys
- Export keys
- Encrypt wallet
- Select connecting remote node
- Custom remote node connection
- Custom local node connection

## How to use

**1. Download the latest release of [GrafenoCoin Lite wallet](https://github.com/elbernn/grafenocoin-lite-wallet/releases/)**

**2. Unpack the release package**

**3. Backup your GrafenoCoin wallet file (skip this step if creating a new wallet)**

**4. Run `GrafenoCoin` and open your wallet file (or create a new one)**

**5. Synchronize with the network**

**6. Use the wallet**

## Troubleshooting

### Ubuntu

- in case of issues starting up the wallet, please run it from the terminal with:

`sudo ./GrafenoCoin`

- in case of missing QT libs please run the following command from the terminal:

`sudo apt-get install -y qt5-default`

### Windows 10

- in case of not being able to start the wallet run it as Administrator
- in case of missing dependencies open the wallet folder and install the file: 'vcredist_x64.exe' 


## How to compile

### Compile on Windows 7/10 (64 bit)

**1. Install dependencies**

Recommended: Microsoft Visual Studio 15 2017, CMake 3.11.3 or later, Boost 1.65 or later and Qt 5.10.x

Get dependencies:
- http://www.microsoft.com
- http://www.cmake.org
- http://www.boost.org
- https://www.qt.io

**2. Get sources & libs**

1. Create an account on [GitHub.com](github.com) or log in to an existing one
2. Fork [GrafenoCoin lite wallet](https://github.com/elbernn/grafenocoin-lite-wallet.git) or/and download it

**3. Configure and generate the project files**

- start CMake GUI and navigate to the repository folder using the field _Where is the source code:_
- in the field _Where to build the binaries:_ specify the build folder location
- click the _Configure_ button to start the configuration
- select STATIC option if it is unchecked
- confirm the creation of the `build` folder at the specified build folder location
- select _Visual Studio 15 2017 Win64_ option.
- click the _Finish_ button to run the configuration
- after the configuration is done, click the _Generate_ button to generate your project files
- after successfull generation click the button _Open project_ to open the project in Visual Studio

**4. Get rocksdb library**

- unzip the _rocksdb.zip_ located in the `lib` folder
- navigate to your `build` folder and go to sub folder `cryptonote/external/rocksdb`
- create a new folder called `Release` and copy the unzipped  _rocksdb.lib_ into the new folder

**5. Build**

- CMake GUI will open the project in the Microsoft Visual Studio you selected for the configuration
- Switch solution to `release`
- wait for the Microsoft Visual Studio to scan and prepare all of the files for the project
- the scan is finished when the message _Ready_ appears
- click the _Build_ button from the main menu

_Your binaries will be located in the `src/release` folder._

### Compile on Ubuntu 16.04 (x64) / 18.04 (x64)

**1. Get dependencies**

`sudo apt-get install -y build-essential python-dev gcc g++ git libboost-all-dev librocksdb-dev qt5-default qttools5-dev-tools cmake`

**2. Get the source**

``
git clone https://github.com/elbernn/grafenocoin-lite-wallet.git grafenocoin-lite-wallet
``

``
cd grafenocoin-lite-wallet/cryptonote/external/rocksdb/build_tools
``

``
chmod +x build_detect_platform version.sh
``

**3. Build**

``
cd && cd grafenocoin-lite-wallet
``

``
mkdir build && cd $_
``

``
cmake -DSTATIC=ON -DCMAKE_BUILD_TYPE=RELEASE ..
``

``
export CXXFLAGS="-std=gnu++11"
``

``
make
``

_Your binaries will be located in the `build/src` folder._
