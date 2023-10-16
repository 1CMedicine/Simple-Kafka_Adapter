# ������ ������� ���������� � ������� Visual Studio 2017
- ��������� boost ������ - 1.68, ��� ��� ��������� ��� �� �������������� VS2017
- ����� ������������ boost - bootstrap.bat, ����� b2.exe
- ��������� https://github.com/microsoft/vcpkg. �� ����������
 ```
 bootstrap-vcpkg.bat
vcpkg integrate install
 ```
����� ����� CMakeSettings.json �� �������. � ��� �������� vcpkg � ��������
- ������� ����� D:\Source\vcpkg\static-triplets � ������� ������� �����
-- x64-windows.cmake � ����������
 ```
set(VCPKG_TARGET_ARCHITECTURE x64)
set(VCPKG_CRT_LINKAGE static)
set(VCPKG_LIBRARY_LINKAGE static)
 ```
-- x86-windows.cmake � ����������
 ```
set(VCPKG_TARGET_ARCHITECTURE x86)
set(VCPKG_CRT_LINKAGE static)
set(VCPKG_LIBRARY_LINKAGE static)
 ```
- ���� ����� ����� lz4, �� �������
 ```
vcpkg remove lz4 --triplet x86-windows
vcpkg remove lz4 --triplet x64-windows
 ```
- ������ ������:
 ```
vcpkg install lz4  --overlay-triplets=static-triplets --triplet x86-windows
vcpkg install librdkafka  --overlay-triplets=static-triplets --triplet x86-windows
vcpkg install lz4  --overlay-triplets=static-triplets --triplet x64-windows
vcpkg install librdkafka  --overlay-triplets=static-triplets --triplet x64-windows
 ```

