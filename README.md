# Get the software set up

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

    radeon-profile-daemon/radeon-profile-daemon/target/radeon-profile-daemon &
    radeon-profile-daemon/radeon-profile-daemon/target/radeon-profile-daemon &

