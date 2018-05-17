# System

## CPU
located at /src/cpu/o3

Focus on O3 CPU 

**DerivO3CPU** ( /src/cpu/o3/deriv.hh ) 

    from FullO3CPU <*O3CPUImpl*>

**FullO3CPU** ( /src/cpu/o3/cpu.hh ) 
    from BaseO3CPU, use tick to simulate, has *fetch*, *decode*, *rename*, *IEW*, *commit* stages inside it 
    
* IcachePort --- TBD
 - recvTimingResp(PacketPtr pkt)
 - recvReqRetry();
* DcachePort --- TBD
 - LSQ \* lsq
 - FullO3CPU \* cpu
 - recvTimingResp(PacketPtr pkt)
 - recvTimingSnoopReq(PacketPtr pkt)
 - recvFunctionalSnoop(PacketPtr pkt)
 - recvReqRetry()
 - isSnooping()
    

**O3CPUImpl** ( /src/cpu/o3/impl.hh ) 



## Cache

## mem_bus

## mem_ctrl

