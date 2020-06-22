# VM-classroom
Recipe for virtualizing the whole classroom (foundation0 and foundationX) on 1 server
so that individual foundationX machines are accessible securely with SPICE protocol with a password

You need:
Server with libvirtd that supports nested virtualization (I used RHEL 8.2) accessible directly on Internet with its own A record or CNAME.
A CA certificate, a key and server certificate issued by the CA in PEM format (I used our existing one and issued a cert for CNAME). It does not need to be a public CA, but self-signed certificate will not work.
Image of USB key with Clasroom content (I used CL310) that you created with rht-usb and RHCIfoundation 8.2 *DO NOT USE ANY OLDER* as nested virtualization is really unstable.

Result:
You as the instructor just need to e-mail the location of SPICE clients and an attached foundationX.vv file that was tailored
for your server.

Linux clients: they should install virt-manager package from their distro repository.
Windows clients:  https://virt-manager.org/download/
Mac OS X clients: https://johnsiu.com/blog/macos-kvm-remote-connect/
                  https://github.com/jeffreywildman/homebrew-virt-manager


 This has allowed me to install foundation0 and 14 foundationX machines for CL310 on a single 32 core EPYC server with 384GiB RAM and two drives (240GB SSD for OS and default libvirt storage and a 3TB Toshiba nVME drive). KSM was saving 100GB of RAM.
