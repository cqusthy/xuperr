<template>
  <div id="app">
   <p @click="test">hhhh</p>
  </div>
</template>

<script>
import XuperSDK from "@xuperchain/xuper-sdk";

export default {
  name: 'App',
  methods:{
    test()
    {

      const node = '127.0.0.1:37101'; // node
      const chain = 'admin'; // chain

       const xsdk = XuperSDK.getInstance({
    node,
    chain,
         env: {
           node: {
             disableGRPC: true // disable gRPC
           }
         }
});

      // const start = async () => {
      //   const acc = xsdk.retrieve("影 放 谓 须 母 强 词 花 钱 蓝 仅 即");
      //   const demo = await xsdk.invokeSolidityContarct(
      //       "test",         // 合约名字
      //       "getO",             // 合约方法
      //       "evm",             // 合约模块，本合约为 evm 合
      //   )
      //   console.log(demo);
      // };
      //
      // start();

      const start = async () => {
        const result = await xsdk.getBlockChains();
        console.log(result);
      };

      start();


    }
  },
}
</script>
