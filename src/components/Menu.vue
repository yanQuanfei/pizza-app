<template>
<div class="row">
    <!-- 菜单 -->
    <div class="col-sm-12 col-md-8">
        <table class="table">
            <thead class="thead-default">
                <tr>
                    <th>尺寸</th>
                    <th>价格</th>
                    <th>加入</th>
                </tr>
            </thead>
            <tbody v-for="item in getMenuItems" :key="item.name">
                <tr>
                    <td>
                        <strong>
                            {{item.name}}
                        </strong>
                    </td>
                </tr>

                <tr v-for="option in item.options" :key="option.size">
                    <td>{{option.size}}</td>
                     <td>{{option.price}}</td>
                      <td><button
                      @click="addToBasket(item,option)"
                       class="btn btm-sm btn-ontline-success">+</button></td>
                </tr>



            </tbody>
        </table>
    </div>
    <!-- 购物车 -->
    <div class="col-sm-12 col-md-4">
        <div v-if="Baskets.length>0">
            <table class="table">
                <thead class="thead-default">
                    <tr>
                     <th>数量</th>
                     <th>品种</th>
                     <th>价格</th>
                    </tr>
               </thead>
                <tbody v-for="item in Baskets" :key="item.name">
                 <tr>
                    <td>
                        <button class="btn btn-sm" @click="delQuantity(item)">-</button>
                        <span>{{item.quantity}}</span>
                        <button class="btn btn-sm" @click="addQuantity(item)">+</button>
                    </td>
                    <td>
                        {{item.name}}{{item.size}}
                    </td>
                    <td>
                       {{item.price * item.quantity}}
                    </td>
                 </tr>
                </tbody>
           </table>
            <p>总价：{{total +"RMB"}}</p>
            <button class="btn btn-success btn-block">提交</button>
        </div>
        <div v-else>
          {{BasketText}}
        </div>


       
    </div>
</div>
</template>

<script>
export default {
    name: "Menu",
    data(){
      return{
          Baskets:[],
          BasketText:"购物车没有任何商品",
        getMenuItems:{
          1: {
            'name': '榴莲pizza',
            'description': '这是喜欢吃榴莲朋友的最佳选择',
            'options': [{
              'size': 9,
              'price': 38
            }, {
              'size': 12,
              'price': 48
            }]
          },
          2: {
            'name': '芝士pizza',
            'description': '芝士杀手,浓浓的芝士丝, 食欲瞬间爆棚',
            'options': [{
              'size': 9,
              'price': 38
            }, {
              'size': 12,
              'price': 48
            }]
          },
          3: {
            'name': '夏威夷pizza',
            'description': '众多人的默认选择',
            'options': [{
              'size': 9,
              'price': 36
            }, {
              'size': 12,
              'price': 46
            }]
          }
        }
      }
    },
    computed:{
        total(){
           let totalCost = 0
           for(let index in this.Baskets)
           {
               let indivItem = this.Baskets[index]
               totalCost += indivItem.quantity * indivItem.price
           }
           return totalCost

        }
        
    },
    methods:{
        addToBasket(item,option){
           let basket = {
                name:item.name,
                size:option.size,
                price:option.price,
                quantity:1
            }

            if(this.Baskets.length>0)
            {
                // 过滤
                let result = this.Baskets.filter((basket)=>{
                    return (basket.name === item.name && basket.price === option.price)
                })

                if (result != null&& result.length > 0)
                {
                    result[0].quantity++
                }else{
                    this.Baskets.push(basket)
                }

            }else{
            this.Baskets.push(basket)
            }
          
        },
        delQuantity(item){
           item.quantity--

           if(item.quantity<=0)
           {
               this.removeFromBaskets(item)
           }
        },
        addQuantity(item){
            item.quantity++
        },
        removeFromBaskets(item){
          this.Baskets.splice(this.Baskets.indexOf(item),1)
        }
    }
    }
</script>

<style scoped>

</style>
