<template>
	<Layout>
		<div  style="width: 100%">
			<div class="index-page">
				<div data-am-widget="tabs" class="am-tabs am-tabs-default">
					<div class="am-tabs-bd">
						<div
							class="am-tab-panel am-active"
							v-if="slideshow.length > 0"
							:style="{ backgroundImage: `url(${slideshow[tabIndex].imageUrl})`}">
							<div class="index-banner">
								<div class="index-mask">
									<div class="container">
										<div class="am-g">
											<div class="am-u-md-10 am-u-sm-centered" style="text-align: center">
												<h1 class="slide_simple--title">知识产权，首选德全</h1>
												<p class="slide_simple--text am-text-left" style="display: flex;justify-content: center">
													选择德全，为您的知识产权保驾护航。我们用心，只为您的成功。
												</p>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
					
					<ul class="am-tabs-nav am-cf index-tab">
						<li v-for="(tab,index) in tabList" :key="index" :class="tabIndex === index ? 'am-active':''" >
							<a href="#" @click.prevent="changeTab(index)">
								<div class="am-u-md-3 am-u-sm-3 am-padding-right-0">
									<i :class="tab.icon"></i>
								</div>
								<div class="school-item-right am-u-md-9 am-u-sm-9 am-text-left">
									<strong class="promo_slider_nav--item_title">{{tab.name}}</strong>
									<p class="promo_slider_nav--item_description">{{tab.desc}}</p>
								</div>
							</a>
						</li>
					</ul>
				</div>
			</div>
		</div>
		
		<div class="section">
			<div class="container" style="max-width: 1160px;">
				<div class="section--header">
					<h2 class="section--title">公司信息</h2>
					<p class="section--description2">
						珠海得全知识产权代理事务所（普通合伙）由多年从业经验的专利代理师组建成立，是经国家知识产权局批准的知识产权代理机构。为客户提供国内外专利、商标、版权申请及企业知识产权法律服务解决方案；另外，还可以为客户提供国家高新技术企业申报、知识产权贯标等各种政策性服务项目。
  					</p>
					<p class="section--description2">
						现有员工学历构成中，硕士学历2人，本科学历8人。以上人员在国内外专利和商标的撰写、答辩、无效、诉讼、维权的相关业务，具有极为丰富的知识产权实务经验。
					</p>
				</div>
				
			</div>
		</div>		
		<div class="section" style="border-bottom: 1px solid #e9e9e9; padding-top: 0">
			<div class="container" style="max-width: 1160px;">
				<div class="section--header">
					<h2 class="section--title">我们的服务-知识产权全产业链服务</h2>
					<p class="section--description2">
						由知识产权诉讼专家、专利代理师、商标代理人和项目辅导师构成中坚力量的专业团队，覆盖计算机、通讯、机械、电子、材料、环境、生物、化工、医药等技术领域。
					</p>
				</div>
				
				<div class="index-container">
					<div class="am-g">
						<div class="am-u-md-3" v-for="(advantage,index) in advantageList" :key="index">
							<div class="features_item">
								<img :src="advantage.cover" alt="">
								<h3 class="features_item--title">{{advantage.title}}</h3>
								<p class="features_item--text">{{advantage.desc}}</p>
							</div>
						</div>
					</div>
				</div>
				<!-- <div class="index-container">
					<div class="am-g">
						<div class="am-u-md-3" v-for="(service,index) in serviceList" :key="index">
							<div class="service_item">
								<i class="service_item--icon" :class="service.icon"></i>
								<h3 class="service_item--title">{{ service.title }}</h3>
								<div class="service_item--text"><p>{{service.desc}}</p></div>
							</div>
						</div>
					</div>
				</div> -->
			</div>
		</div>
	</Layout>
</template>

<script>
import Layout from "@/components/common/Layout";
export default {
	name: "IndexView",
	components: {Layout},
	data(){
		return{
			tabList:[
				{name:'广州分公司', desc:'', icon:'am-icon-flag'},
				{name:'珠海分公司', desc:'', icon:'am-icon-flag-checkered'},
				{name:'江门分公司', desc:'', icon:'am-icon-flag-o'},
			],
			tabIndex: 0,
			slideshow:[],
			
			advantageList:[
				{id:1,cover:require('../assets/images/index/zhuanliquan.png'),title:'专利权',desc:''},
				{id:2,cover:require('../assets/images/index/zhuanlijiansuo.png'),title:'专利检索',desc:''},
				{id:3,cover:require('../assets/images/index/shangbiaozhuce.png'),title:'商标注册',desc:''},
				{id:4,cover:require('../assets/images/index/sifa.png'),title:'司法',desc:''},
			],
			serviceList:[
				{id:1,icon:'am-icon-diamond',title:'多页面工作',desc:'标签栏可切换，不必为了新内容而被迫跳转界面，多项工作内容并行处理'},
				{id:2,icon:'am-icon-user',title:'多页面工作',desc:'标签栏可切换，不必为了新内容而被迫跳转界面，多项工作内容并行处理'},
				{id:3,icon:'am-icon-umbrella',title:'多页面工作',desc:'标签栏可切换，不必为了新内容而被迫跳转界面，多项工作内容并行处理'},
				{id:4,icon:'am-icon-briefcase',title:'多页面工作',desc:'标签栏可切换，不必为了新内容而被迫跳转界面，多项工作内容并行处理'}
			]
		}
	},
	mounted() {
		this.getSlideshow()
	},
	methods:{
		changeTab(index){
			this.tabIndex = index
		},
		getSlideshow(){
			this.getRequest("/findAllSlideshow").then(resp =>{
				if (resp){
					this.slideshow = resp.data.data
					//console.log(this.slideshow)
				}
			})
		}
	},
}
</script>

<style scoped>

</style>
