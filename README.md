# VM-classroom
Recipe for virtualizing the whole classroom (foundation0 and foundationX) on 1 server
so that individual foundationX machines are accessible securely with SPICE protocol with a password

You need:
Server with libvirtd that supports nested virtualization (I used RHEL 8.2) accessible directly on Internet with its own A record or CNAME.
A CA certificate, a key and server certificate issued by the CA in PEM format (I used our existing one and issued a cert for CNAME). It does not need to be a public CA, but self-signed certificate will not work.
Image of USB key with Clasroom content (I used CL310) that you created with rht-usb and RHCIfoundation 8.2 *DO NOT USE ANY OLDER* as nested virtualization is really unstable.



 
