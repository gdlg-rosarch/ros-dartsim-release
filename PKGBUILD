# Script generated with Bloom
pkgdesc="ROS - DART (Dynamic Animation and Robotics Toolkit) is a collaborative, cross-platform, open source library created by the Georgia Tech Graphics Lab and Humanoid Robotics Lab, with ongoing support by the University of Washington Personal Robotics Lab and Open Robotics. DART provides data structures and algorithms for kinematic and dynamic applications in robotics and computer animation."
url='http://dartsim.github.io/'

pkgname='ros-kinetic-dartsim'
pkgver='6.3.1_3'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('assimp'
'boost'
'bullet'
'cmake'
'eigen3'
'fcl'
'flann'
'freeglut'
'libxi'
'libxmu'
'pkg-config'
'tinyxml'
'tinyxml2'
'urdfdom'
)

depends=('assimp'
'boost'
'bullet'
'eigen3'
'fcl'
'flann'
'freeglut'
'libxi'
'libxmu'
'ros-kinetic-catkin'
'tinyxml'
'tinyxml2'
'urdfdom'
)

conflicts=()
replaces=()

_dir=dartsim
source=()
md5sums=()

prepare() {
    cp -R $startdir/dartsim $srcdir/dartsim
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

