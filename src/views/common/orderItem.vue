<template>
    <div class="item">
      <router-link to="/orderDetail">
        <img src="http://via.placeholder.com/300/300"  alt=""/>
      </router-link>
      <div class="info">
        <router-link to="/orderDetail" >
            <div class="name">甲方乙方</div>
         </router-link>
            <div class="no">注册号：55555555</div>
            <div class="category">类别：类别</div>
            <div class="expire">注册公告日期：2017-11-23 10:20:30</div>
            <div class="price">￥17990</div>
       
            <div class="status" v-if="status!=null||status!=undefined">{{status}}</div>
        <div class="desc">核准商品/服务：商品服务列表，如果过长就隐藏部分，点击详情查看全部</div>
      </div>
    </div>
</template>

<script>
export default{
    props:['status']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.item {
    padding: 0.1rem;
    position: relative;
    border-radius: 0.1rem;
    background: #fff;
    margin-top: 0.1rem;
    height: 2.7rem;
    overflow: hidden;
    position: relative;
}

.item img {
    width: 2.1rem;
    height: 2.7rem;
}

.info {
    display: inline-block;
    vertical-align: top;
    font-size:0.22rem;
    margin-left: 0.1rem;
    max-width: 60%;
}

.name {
    font-size: 0.32rem;
    color:#333;
    font-weight: bold;
    margin-top: 0.1rem;
}

.no {
    margin-top: 0.1rem;
    color: #999;    
    line-height: 0.3rem;
}

.category {
    color: #999;
    line-height: 0.3rem;
}

.expire {
    color: #999;
    line-height: 0.3rem;
}

.desc {
    /*width: 80%;*/
    margin-top: 0.3rem;
    color: #666;
    overflow: hidden;
    text-overflow: ellipsis;
    -webkit-line-clamp: 1;
    -webkit-box-orient: vertical;
    display: -webkit-box;
    line-height: 0.3rem;

}

.btn-favorite {
    position: absolute;
    width: 1rem;
    height: 0.3rem;
    line-height: 0.3rem;
    text-align: center;
    font-size: 0.18rem;
    border-radius:0.05rem;
    right: 0.2rem;
    top: 0.2rem;
}
.btn-freeze {
    position: absolute;
    width: 1.2rem;
    height: 0.3rem;
    line-height: 0.3rem;
    text-align: center;
    color: #f52e2e;
    font-size: 0.24rem;
    border-radius:0.05rem;
    right: 0.2rem;
    top: 0.6rem;
}
.price {
    color: #f52e2e;
    margin-top: 0.2rem;
    border-bottom: 0.01rem solid rgb(244,244,244);
    line-height: 0.4rem;
    font-size: 0.28rem;
}
a {
    text-decoration: none;
}
.status{
    position: absolute;
    padding: 0.1rem;
    height: 0.2rem;  
    top: 0.2rem;
    right: 0.2rem;
    background:#ccc;
    border-radius: 0.1rem;
}
</style>
