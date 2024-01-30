<template>
	<div class="footer">
		<div style="background-color:#383d61" class="footer--bg"></div>
		<div class="footer--inner">
			<div class="am-g">
				<div class="am-u-md-3 ">
					<div class="footer_main--column">
						<strong class="footer_main--column_title">公司</strong>
						<ul class="footer_navigation">
							<li class="footer_navigation--item"><router-link to="/product" class="footer_navigation--link">广州分公司</router-link></li>
							<li class="footer_navigation--item"><router-link to="/product" class="footer_navigation--link">珠海分公司</router-link></li>
							<li class="footer_navigation--item"><router-link to="/product" class="footer_navigation--link">江门分公司</router-link></li>
						</ul>
					</div>
				</div>
				<div class="am-u-md-6 ">
					<div class="footer_main--column">
						<strong class="footer_main--column_title">关于我们</strong>
						<div class="footer_about">
							<p class="footer_about--text">
								德全，您的知识产权贴心管家，提供专业、高效的全方位服务，保障您的创新成果安全无忧。
							</p> 
						</div>
					</div>
				</div>
				<div class="am-u-md-3 ">
					<div class="footer_main--column">
						<strong class="footer_main--column_title">联系详情</strong>
						<ul class="footer_contact_info">
							<li class="footer_contact_info--item"><i class="am-icon-phone"></i><span>服务专线：13189856931</span></li>
							<li class="footer_contact_info--item"><i class="am-icon-map-marker"></i><span>广东省广州市</span></li>
							<li class="footer_contact_info--item"><i class="am-icon-clock-o"></i><span>周一 ~ 周日, 8:00 - 23:00 </span></li>
						</ul>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: "Footer"
}

</script>

<style scoped>

</style>
