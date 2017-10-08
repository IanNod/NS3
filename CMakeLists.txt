#######################################
# Required CMake version#
#######################################
cmake_minimum_required( VERSION 3.0 )

#######################################
# Project name                        #
#######################################
project(NS3 CXX)

include(buildsupport/macros_and_definitions.cmake)

set(NS3_VER 3.26)

set(NS3_TESTS OFF)
option(NS3_TESTS "Enable tests to be built" OFF)

set(NS3_DEBUG ON)
option(NS3_DEBUG "Build NS3-lib in debug mode" OFF)

#set(NS3_PTHREAD ON)
#option(NS3_PTHREAD "Build with pthread support" OFF)

set(NS3_BOOST ON)
option(NS3_BOOST "Build with Boost support" OFF)

set(NS3_GTK2 ON)
option(NS3_GTK2 "Build with GTK2 support" OFF)

set(NS3_LIBXML2 ON)
option(NS3_LIBXML2 "Build with LIBXML2 support" OFF)

set(NS3_LIBRT ON)
option(NS3_LIBRT "Build with RT support" OFF)

set(NS3_MPI ON)
option(NS3_MPI "Build with MPI support" OFF)

set(NS3_GSL ON)
option(NS3_GSL "Build with GSL support" OFF)

#Select libs to be built
set(libs_to_build
        antenna
        aodv
        applications
        bridge
        #brite
        buildings
        click
        config-store
        core
        csma
        csma-layout
        dsdv
        dsr
        energy
        fd-net-device
        flow-monitor
        internet
        internet-apps
        lr-wpan
        lte
        mesh
        mobility
        mpi
        netanim
        network
        nix-vector-routing
        olsr
        #openflow
        point-to-point
        point-to-point-layout
        propagation
        sixlowpan
        spectrum
        stats
        #tap-bridge
        #test
        topology-read
        traffic-control
        uan
        virtual-net-device
        #visualizer
        wave
        wifi
        wimax
        )


#######################################
# Process options                     #
#######################################
process_options()


#######################################
# Add subdirectories                  #
#######################################
NS3_common_includes()

#Build NS3 3rd-party library support
add_subdirectory(3rd-party)

#Build NS3 library core
add_subdirectory(src)

#Build contribution libraries
#add_subdirectory(contrib)

#Build scratch/simulation scripts
#add_subdirectory(scratch)



