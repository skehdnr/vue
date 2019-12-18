<template>
<div>
	<Nav></Nav>
	<div id="example" class="container layout1">
		<p><input type="text" v-model="amount" class="form-control" /></p>
		<p>
			<button id="create" @click.once="specialEvent"
			class="btn btn-primary">계좌 개설 10000원 이벤트</button>
			<button  @click="deposit($event)"
				class="btn btn-primary">예금</button>
			<button @click="withdraw"
				class="btn btn-primary">인출</button>
		</p>            
		<h3>계좌 잔고 : {{balance}}</h3>
	</div>
	<Footer></Footer>
</div>
</template>
<script>
import Nav from "@/components/cmm/Nav.vue"
import Footer from "@/components/cmm/Footer.vue"
export default{
	name : "account",
	components : {
		Nav, Footer
	},
	data(){
		return {
			amount : '',
			balance : 0
		}
	},
	methods : {
		specialEvent(){
			this.balance = 10000
		},
		deposit(){
			alert(`입금액 : ${this.amount}`)
			this.balance += Number(this.amount)
		},
		withdraw(){
			this.balance -= Number(this.amount)
		}
	}
}
</script>
<style scoped>
 .layout1 { margin:30px 30px 30px 30px; }
</style>