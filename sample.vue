<!-- HTML 시작 !-->
<div id="app">
	<v-app id="inspire">
		<div>
			<v-row no-gutters>
				<v-card color="black" width="100%">
					<div style='text-align:center'>
						<span class="time">2020-03-14 12:00:00</span>
					</div>
				</v-card>
			</v-row>
			<v-responsive width="100%">
				<template v-for="item in machine">
					<v-col :key="item.idx">
						<v-card>
							<v-row style="margin-left:0;margin-right:0;">
								<v-toolbar dense flat color="#e1f6fa" height="50">
								<span class="f_mname">{{item.mid}}</span>
									<v-spacer></v-spacer>
								<span class="f_p">{{item.process}}</span>
								</v-toolbar>
							</v-row>
							<div class="text-center">
								<span class="f_end">{{item.timer}}</span>
							</div>
							<v-footer height="50" class="white">
								<v-row>
									<v-progress-linear v-bind:value="item.percent" height="40" color="#0054ff" background-color="#bebebe" rounded>
										<v-flex style="maxWidth:20px"></v-flex>
										<span class="vt">{{ item.count}}</span>
										<v-spacer></v-spacer>
										<span class="vt">
											<div class="text-right">{{item.fTime}}</div>
										</span>
										<v-flex style="maxWidth:20px"></v-flex>
									</v-progress-linear>
								</v-row>
							</v-footer>
						</v-card>
					</v-col>
				</template>
			</v-responsive>
		</div>
	</v-app>
</div>
<!-- HTML 끝 !-->

<style>
<!-- CSS 시작 !-->
.v-application--wrap{
 background:#a0a0a0;
}
.time{
	font-size: 26px;
	color: #fff;
	text-align: center;
}
.f_mname{
	font-size: 20px;
}
.f_p {
	font-size: 20px;
}
.vt {
	font-size: 16px;
	color: #fff;
}
.f_end {
	font-size: 18px;
}
.v-responsive__content::after{clear:both; content:''; display:block;}
.col{width:33.33%; float:left;}
@media (max-width:1080px){
	.col{width:50%; float:left;}
}
@media (max-width:768px){
	.col{width:100%; float:inherit;}
}
<!-- CSS 끝 !-->
</style>

<script>
<!-- JS 시작 !-->
new Vue({
	el: '#app',
	vuetify: new Vuetify(),
	data () {
	return {
		tab: null,
		machine: [
		{
			mid : 'Puma280',
			idx : 1,
			process : 'CS98D25H49-01-2',
			timer : '가공완료',
			count : '100/100',
			fTime : '0 시간 6 분',
			percent : 100,
		},
		{
			mid : 'PumaV400',
			idx : 2,
			process : 'O0229',
			timer : '04:34',
			count : '4/100',
			fTime : '84 시간 40 분',
			percent : 4,
		},
		{
			mid : 'Lynx220C',
			idx : 3,
			process : 'D580007-02-F',
			timer : '01:33',
			count : '459/500',
			fTime : '2 시간 36 분',
			percent : 91.8,
		},
		{
			mid : 'Puma240',
			idx : 4,
			process : 'WGR150D35H24-02-1',
			timer : '00:10',
			count : '70/100',
			fTime : '1 시간 31 분',
			percent : 70,
		},
		{
			mid : 'Lynx220CL',
			idx : 5,
			process : 'CS98D25H49-02-02',
			timer : '02:34',
			count : '12/100',
			fTime : '5 시간 0 분',
			percent : 12,
		},
		{
			mid : 'Lynx220SY',
			idx : 6,
			process : 'JIG-CD',
			timer : 'READY',
			count : '110/200',
			fTime : '23 시간 48 분',
			percent : 55,
		},
		],
	}
	},
})
<!-- JS 끝 !-->
</script>