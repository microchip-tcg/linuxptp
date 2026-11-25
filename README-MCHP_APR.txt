In builds compiled with compiler flag define ~MCHP_APR~, 
APR receives timestamp information from ptp4l and controls
the TSU and PHC.

Note: Only supports E2E delay mechanism. Configure ~delay_mechanism E2E~ for every
PTP interface used by ~ptp4l~.
  
The P2P, COMMON_P2P (CMLDS), Auto, and NONE delay mechanisms are not
supported in APR mode. P2P and CMLDS require peer-delay measurements
that the APR timestamp bridge does not currently provide. Auto is
unsupported because it may select P2P.
  
APR controls the TSU and PHC. Other LinuxPTP utilities retain their
normal clock-adjustment behavior, but using them to adjust the
APR-controlled PHC while APR is active may conflict with APR.
