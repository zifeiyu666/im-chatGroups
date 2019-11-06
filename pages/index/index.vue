<template>
	<view>
		<view class="list" v-for='(item, index) in list' :key='index'>
			<view class="avatar" v-if='item.avatarList.length > 9'>
				<img :src="i" alt="" class='avatar-img-small' v-for='(i, index) in item.avatarList.slice(0,9)' :key='index'>
			</view>
			<view class="avatar" v-else-if='item.avatarList.length > 4'>
				<img :src="i" alt="" class='avatar-img-small' v-for='(i, index) in item.avatarList' :key='index'>
			</view>
			<view class="avatar" v-else-if='item.avatarList.length > 1'>
				<img :src="i" alt="" class='avatar-img-middle' v-for='(i, index) in item.avatarList' :key='index'>
			</view>
			<view class="avatar" v-else>
				<img :src="i" alt="" class='avatar-img-big' v-for='(i, index) in item.avatarList' :key='index'>
			</view>
			<view class="content">
				<view class="title">
					<text class='title-text'>{{item.name}}</text>
					<text class="time">{{item.lastMsg.time}}</text>
				</view>
				<view class='msg'>{{item.lastMsg.username}}:{{item.lastMsg.msg}}</view>
			</view>
		</view>
	</view>
	
</template>

<script>
	import demoList from '@/demo.json'
	export default {
		data() {
			return {
				title: 'Hello',
				list: demoList.list
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.list{
		display: flex;
		/* margin-bottom: 20upx; */
		padding: 20upx;
	}
	.avatar{
		background-color: #F1F1F1;
		border-radius: 8upx;
		min-width: 100upx;
		max-width: 100upx;
		min-height: 100upx;
		max-height: 100upx;
		display: flex;
		justify-content: center;
		align-items: center;
		align-content: center;
		flex-wrap: wrap-reverse;
		margin-right: 20upx;
	}
	.avatar-img-big{
		width: 98%;
		margin: 1%;
	}
	.avatar-img-middle{
		width: 47%;
		margin: 1%;
	}
	.avatar-img-small{
		width: 31%;
		margin: 1%;
	}
	.title{
		font-size: 32upx;
		width: 100%;
		display: flex;
		justify-content: space-between;
	}
	.title-text{
		overflow: hidden;
		text-overflow: ellipsis;
		white-space: nowrap;
	}
	.time{
		font-size: 28upx;
		color: #C0C0C0;
		white-space: nowrap;
	}
	.content{
		overflow: hidden;
		flex-grow: 1;
		justify-content: center;
		display: flex;
		flex-direction: column;
	}
	.msg{
		width: 100%;
		font-size: 28upx;
		color: #C0C0C0;
		overflow: hidden;
		text-overflow:ellipsis;
		white-space: nowrap;
	}
</style>
