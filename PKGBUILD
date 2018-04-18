# Script generated with Bloom
pkgdesc="ROS - This package contains a tool for setting and publishing joint state values for a given URDF."
url='http://www.ros.org/wiki/joint_state_publisher'

pkgname='ros-melodic-joint-state-publisher'
pkgver='1.12.13_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-melodic-catkin'
'ros-melodic-rostest'
)

depends=('ros-melodic-python-qt-binding'
'ros-melodic-rospy'
'ros-melodic-sensor-msgs'
)

conflicts=()
replaces=()

_dir=joint_state_publisher
source=()
md5sums=()

prepare() {
    cp -R $startdir/joint_state_publisher $srcdir/joint_state_publisher
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
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

