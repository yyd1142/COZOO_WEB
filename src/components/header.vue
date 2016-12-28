<template>
	<div id="header">
		<nav class="header-view">
			<div class="header-logo"></div>
			<ul class="header-table-view">
				<li class="header-table-cell" :class="item.active" v-for="(item, index) in headItems" @click="tab(item, index)">
					<a v-text="item.title"></a>
				</li>
                <li class="header-table-cell" style="margin: 0 -12px 0 20px;">
					<a>/</a>
				</li>
                <li class="header-table-cell">
					<a>简体中文</a>
				</li>
                <li class="header-table-cell">
					<a>English</a>
				</li>
			</ul>
		</nav>
	</div>
</template>
<script type="text/javascript">
var headItems = [{name: 'home', active: 'home-active', url: '/#home', title: '首页'},
{name: 'mission', active: '', url: '/#mission', title: '使命'},
{name: 'about', active: '', url: '/#about', title: '关于从筑'},
{name: 'core', active: '', url: '/#core', title: '核心团队'},
{name: 'adviser', active: '', url: '/#adviser', title: '顾问团队'}];
export default {
    data() {
        return {
            headItems: headItems
        }
    },
	methods: {
		tab(item, index){
			let self = this;
			this.headItems.forEach(function(obj){
				if(self.headItems.indexOf(obj) == index){
					obj.active = 'home-active';
				}else{
					obj.active = '';
				}
			});
			window.location.href = item.url;
		}
	}
}
</script>