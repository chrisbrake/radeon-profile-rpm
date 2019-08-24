# Get the software set up

    rm -rf build
    mkdir build
    pushd build

        git clone https://github.com/marazmista/radeon-profile.git
        pushd radeon-profile/radeon-profile
        qmake-qt5 && make
        popd

        git clone https://github.com/marazmista/radeon-profile-daemon.git
        pushd radeon-profile-daemon/radeon-profile-daemon
        qmake-qt5 && make
        popd

    popd

# Run the daemon first, and then the front end

    sudo ./build/radeon-profile-daemon/radeon-profile-daemon/target/radeon-profile-daemon &
    ./build/radeon-profile/radeon-profile/target/radeon-profile &

