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
* tick --- ***main code***
    simply tick every stage
    - fetch.tick() ( /src/cpu/o3/fetch_impl.hh )
    - decode.tick() ( /src/cpu/o3/decode_impl.hh )
    - rename.tick() ( /src/cpu/o3/rename_impl.hh )
    - IEW.tick() ( /src/cpu/o3/iew_impl.hh )
    - commit.tick() ( /src/cpu/o3/commit_impl.hh )
    
   
**IEW** ( /src/cpu/o3/iew_impl.hh )

stage for issue, execute and writeback 

* dispatch()
* executeInsts() --- ***focus***
    - instQueue.getInstToExecute()  ( inst_queue_impl.hh ) We have a instruction queue (instQueue), which stores all the dispatched instructions 
    - fault = ldstQueue.executeLoad(inst) （lsq_impl.hh） If it is load, we need to read from memory system
        - calls the executeLoad function of a lsq_unit (lsq_unit_impl.hh)
            - load_fault = inst->initiateAcc() --- inst is a impl::DyInstPtr class, where impl = O3CPUImpl  
    - fault = ldstQueue.executeStore(inst);
    
* writebackInsts()



**O3CPUImpl** ( /src/cpu/o3/impl.hh ) 



## Cache

## mem_bus

## mem_ctrl

