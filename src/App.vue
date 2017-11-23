<template>
<div id='app'>
    <!--导航栏1366部分开始-->
    <div class="infinox-large">
        <div class="container">
            <div class="infinox-left">INFINOX
            </div>  
            <div class="infinox-right">
                 <i>Mr.Wang</i><b>&#9660</b>    
            </div>   
            <div class="infinox-center">
                <ul>
                    <li>Home</li>
                    <li>Transaction</li>
                    <li>IB Management</li>
                    <li  class="change">Trade Management</li>
                    <li>Trading Tools</li>
                    <li>Contact Us</li>
                </ul>
            </div>    
        </div>
     </div>
    <!-- 导航栏1366部分结束 -->
    <!-- 导航栏768和320部分开始 -->
     <div class="infinox-small">
            <div class="infinox-left">三
            </div>  
             <div class="infinox-right">
                 <i>Mr.Wang</i><b>&#9660</b>    
            </div>  
            <div class="infinox-center">
                INFINOX
            </div>     
    </div>
    <!-- 导航栏768和320部分结束 -->
    <!-- Deposit部分开始 -->
    <div class="deposit container">
        <!-- 标题部分 -->
        <div class="deposit-top">Deposit</div>
        <!-- deposit下半部分开始 -->
        <div class="deposit-bottom clearfix">
            <div class="deposit-B-left ">
                <div class="deposit-B-left-title">
                    <div class="rect"></div>
                    <div class="text">We support the following payment methods:</div>
                </div>
                <div class="deposit-B-left-img clearfix">
                    <ul >
                         <li v-for='val in depositWay' v-on:click="classControll(val)"  :class="{'active':selected==val}" >
                            <div><div></div></div>
                            <p>{{val}}</p>
                        </li>
                    </ul>
                </div>
                <div class="deposit-B-left-intruce clearfix" v-show="selected=='Bank/Credit Card'">
                     <h4>Bank/Credit Card</h4>
                     <div>Bank and Credit are an easy way to fund your account and allow you to fund you INFINOX accout the same day. if you would like to fund your INFINOX Live Account via bank/credit card,please fill in the amount and currency you wish to fund with and click Deposit. Please be aware that we have strict measure in place to protext both our clients and INFINOX from fraud issues.<br>
                    <i>1.75% free is added automatically for credit card transactions 
                    Your deposit is in the same currency as INFINOX Trading Account
                    </i>
                     </div>
                </div>
                <div class="deposit-B-left-account clearfix">
                    <div class="rect"></div>
                    <div class="text">We support the following payment methods:</div>
                </div>
                <div class="deposit-B-left-data clearfix">
                    <ul>
                        <li>
                            <span>10001931</span><span>USD0</span>
                        </li>
                        <li>
                            <span>10001931</span><span>USD0</span>
                        </li>
                        <li>
                            <span>10001931</span><span>USD0</span>
                        </li>
                    </ul>
                </div>
                <div class="deposit-B-left-Note" v-show="selected=='Bank Transter'">
                  <div>NOTE:Found your account in your accounts currency.Example</div>
                  <div>EUR account-Found using EUR bank account details</div>
                  <div>EUR account-Found using EUR bank account details</div>
                  <div>EUR account-Found using EUR bank account details</div></div>
                <div class="deposit-B-left-button">
                    <button type="">Deposit History</button>
                </div>
            </div>
            <div class="deposit-B-right">
                <div class="deposit-B-right-title clearfix">
                    <div class="rect"></div>
                    <div class="text">Deposit funds to your account</div>
                </div>
                <div class='deposit-B-right-account'>
                    <div>Your account</div>
                    <select >
                        <option value="">10001931</option>
                        <option value="">10001931</option>
                        <option value="">10001931</option>
                    </select>
                </div>
                <div class="deposit-B-right-enterAccount">
                    <div>Enter account</div>
                    <input type="text" name="" value="">
                </div>
                <div class="deposit-B-right-RMBPay" v-show="selected=='China Union Pay'">
                    <span>RMB to be paid:</span><input type="text" value="5">
                </div>
                <div class="deposit-B-right-payment">
                     <div>Please consirm your parment method from the list below.</div>
                    <select v-model="selected" v-on:change="selectChange(selected)">
                        <option selected="selected">Bank/Credit Card</option>
                        <option>Select</option>
                        <option>Skrill</option>
                        <option>Neteller</option>
                        <option>China Union Pay</option>
                        <option>Bank Transter</option>
                    </select>
                </div>
                <div class="deposit-B-right-intruce  clearfix" v-show="selected=='Bank Transter'">
                     <h4>Bank Transfer</h4>
                     <div>Bank and Credit are an easy way to fund your account and allow you to fund you INFINOX accout the same day. if you would like to fund your INFINOX Live Account via bank/credit card,please fill in the amount and currency you wish to fund with and click Deposit. Please be aware that we have strict measure in place to protext both our clients and INFINOX from fraud issues.<br>
                     Bank:Barclays<br>
                     Bank Address:1 Churchill place,London,E14 5HP

                     </div>
                </div>
                <div class="deposit-B-right-cardNum" v-show="selected=='Bank/Credit Card'">
                     <div>Card Number</div>
                    <input type="text" name="" value="">
                </div>
                <div class="deposit-B-right-HolderName" v-show="selected=='Bank/Credit Card'">
                    <div>Card Holder Name</div>
                    <input type="text" name="" value="">
                </div>
                <div class="deposit-B-right-date clearfix" v-show="selected=='Bank/Credit Card'">
                    <div class="left fl">
                        <div>Expiratin Date</div>
                        <div ><input type="text" value="MM">
                        <input type="text" value="YY"></div>
                    </div>
                    <div class="right fr">
                        <div>CVV Code</div>
                        <div><input type="text" class="fr" value="CVV"></div>
                    </div>
                </div>
                <div class="deposit-B-right-debited clearfix" v-show="selected=='Bank/Credit Card'">
                    <div class="deposit-B-right-text fl">
                         <h5>Amount Debited:$0.00</h5>
                         <div>The data of your credit card is used only at the time of the transaction and are transmitted over a secure protocol to the acquiring bank in encryted. Details of your card are not stored in the system and,ancoordingly,can not be transferred to find parties</div>
                    </div>
                    <div class="deposit-B-right-img fr"></div>
                </div>
                <div class="deposit-B-right-Msg" v-show="selected=='Skrill'">
                     <div>Amount Debited:$0<br>
                    Skrill payments are charged a 2.5% + 0.15 EUR transaction fee</div>
                </div>
                <div class="deposit-B-right-Msg" v-show="selected=='Neteller'">
                     <div>Amount Debited:$0<br>
                    Neteller payments are charged a 2.5% + 0.15 EUR transaction fee</div>
                </div>
                <div class="deposit-B-right-button">
                    <button>FUND NOW</button>
                </div>
            </div>
        </div>
        <!-- deposit下半部分结束 -->
        <!-- deposit底部开始 -->
        <!-- deposit底部结束 -->
    </div>
    <div class="deposit-footer" v-show="selected=='Bank Transter'">
            <table >
                <thead>
                    <tr>     
                        <th>ACCOUNT currency</th>
                        <th>GBP</th>
                        <th>EUR</th>
                        <th>USD</th>
                        <th>JPY</th>
                        <th>SGD</th>
                        <th>AUD</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>SORT CODE</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                    </tr>
                    <tr>
                        <td>ACCOUNT NUMBER</td>
                        <td>23349802</td>
                        <td>43456666</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                    </tr>
                     <tr>
                        <td>SWIFT</td>
                        <td>23349802</td>
                        <td>43456666</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                    </tr>
                     <tr>
                        <td>IBAN</td>
                        <td>23349802</td>
                        <td>43456666</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                        <td>200000</td>
                    </tr>
                    <tr>
                        <td>REFERENCE</td>
                        <td colspan="6">YOUR INFINOX ACCOUNT LOGIN</td>
                    </tr>
                </tbody>
            </table>
            <div><i>+</i>You should have received these setails in your original account opening email,if you have misplaced this email or need a refresher,simply email</div>
    </div>
    <div class="deposit-last">
        <div>@2016 Trading FOREX FX,Cuboid Options and CFD's is high risk.Losses can exceed deposits</div>
    </div>
</div>

</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      pageView:'',
      selected:'',
      depositWay:['Bank/Credit Card','Skrill','Neteller','China Union Pay','Bank Transter']
    }
  },
  methods:{
     selectChange:function(num){
      this.pageView = num;
     },
     classControll:function(data){
       this.selected = data;
     }
  }
}
</script>

<style>

html,body,h1,h2,h3,h4,h5,h6,div,dl,dt,dd,ul,ol,li,ptable,caption,th,td,form,fieldset,legend,input,button,textarea,menu{
    margin:0;padding:0;
    font-size:12px;
}
header,footer,section,article,aside,nav,hgroup,address,figure,figcaption,menu,details{
    display:block;
}
table{
    border-collapse:collapse;border-spacing:0;
}
caption,th
{
    text-align:left;
    font-weight:normal;
}
html,body,fieldset,img,iframe,abbr{
    border:0;
}
i,em{
    font-style:normal;
}

li{
    list-style:none;
    float:left;
}
h1,h2,h3,h4,h5,h6{
    font-size:100%;
}
body{background:#151515;}
.container {
    width: 90%;
    margin:0 auto;
}
.change {
    color:#F5C603;
    border-bottom:2px solid #F5C603;
}

.hide {
    display:none;
}
.show {
    display: block;
}
.clearfix:before,.clearfix:after {
    content: "";
    display: block;
     clear: both;
 }
  .clearfix {
    zoom: 1;
 }
.fl {
    float:left;
}
.fr {
    float:right;
}
body,html {
    height: 100%;
    width: 100%;
}
.height {
    height: calc(100vh - 120px);
}
.bankCredit {
      background: url("../deposit/icon_card.png") no-repeat bottom;
      width: 46px;
      height: 33px; 
}

.deposit-B-left-img ul li.active div div {
  background-position:bottom  !important; 
}
.deposit-B-left-img ul li.active p {
  color:#F5C603 !important;
}
</style>
