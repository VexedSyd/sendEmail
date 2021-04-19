# sendEmail
sendEmail v1.56 Perl Script updated with TLSv1.2 and TLSv1.3 Support
The original script and exe support TLSv1.0 only. 
Original script and exe can be found here:
http://caspian.dotconf.net/menu/Software/SendEmail/

In order to pack the exe properly with all the dependencies and rerequired DLLs, you have to use pp_autolink.
https://metacpan.org/pod/App::PP::Autolink

This was tested successfully with 
Strawberry Perl 5.32.1.1 x64 Portable.
Net::SSLeay v1.90.
IO::Socket::SSL v2.070.

Make sure to install these required modules then, pp_autolink -o sendEmail.exe sendEmail.pl

Please note, pp (PAR Packager) fails to link the required libraries, use pp_autolink.

Test sendEmail.exe with -o tls=yes to confirm the required DLLs are linked properly.

If successful, the packed executable will support TLSv1.2 and TLSv1.3.

Please note, if you are having trouble with SSL certificate verification (i.e. invalid certificates are being used on the STMP server), then look for the below line and comment it.
IO::Socket::SSL::set_defaults(SSL_verify_mode => 0). Please research security implications of such change (MitM attacks, etc).

