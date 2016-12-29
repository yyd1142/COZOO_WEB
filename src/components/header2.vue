<template>
	<div id="header">
		<nav class="header-view2">
			<div class="header-logo2"></div>
			<ul class="header-table-view2">
				<li class="header-table-cell2" :class="item.active" v-for="(item, index) in headItems" @click="tab(item, index)">
					<a v-text="item.title"></a>
				</li>
                <li class="header-table-cell2" style="margin: 0 -12px 0 20px;">
                    <div class="cong-zhu-btn">从筑</div>
				</li>
			</ul>
		</nav>
	</div>
</template>
<script type="text/javascript">
var headItems = [{name: 'main', active: 'home-active2', url: '/pic#main', title: '首页'},
{name: 'project', active: '', url: '/pic#project', title: '项目介绍'},
{name: 'experience', active: '', url: '/pic#experience', title: '项目体验'},
{name: 'picture', active: '', url: '/pic#picture', title: '项目图库'},
{name: 'story', active: '', url: '/pic#story', title: '记实'},
{name: 'product', active: '', url: '/pic#product', title: '产品'},
{name: 'reserve', active: '', url: '/pic#reserve', title: '民宿预定'},
{name: 'contacts', active: '', url: '/pic#contacts', title: '联系从筑'}];
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
					obj.active = 'home-active2';
				}else{
					obj.active = '';
				}
			});
			window.location.href = item.url;
		}
	}
}
</script>