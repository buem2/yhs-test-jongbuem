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
				<template v-for="item in machine">
					<v-col :key="item.idx">
						<v-card>
							<v-row>
								<v-toolbar dense flat color="#b5b5b5" height="120">
									<span class="f_mname">{{item.mid}}</span>
									<v-spacer></v-spacer>
									<span class="f_p">{{item.process}}</span>
								</v-toolbar>
							</v-row>
							<div class="text-center">
								<div class="f_end">
									{{item.timer}}
								</div>
							</div>
							<v-footer :fixed="true" height="100" absolute class="white">
								<v-row>
									<v-progress-linear value="15" height="94"
													   color="#357d21" background-color="#828282" rounded>
										<v-flex style="maxWidth:20px"></v-flex>
										<span class="vt">{{ item.count}}</span>
										<v-spacer></v-spacer>
										<span class="vt">
											<div class="text-right">{{ item.fTime }}</div>
										</span>
										<v-flex style="maxWidth:20px"></v-flex>
									</v-progress-linear>
								</v-row>
							</v-footer>
						</v-card>
					</v-col>
				</template>
			</v-row>
		</div>
	</v-app>
</div>
<!-- HTML 끝 !-->

<style>
<!-- CSS 시작 !-->
body {
	height: 100%;
}
.no-gutters {
	height: 100%;
}
.v-card.v-sheet.theme--light.black {
	height: 10%;
}
.v-card.v-sheet.theme--light.black>div {
	height: 100%;
	display: flex;
	align-items: center;
	justify-content: center;
}
.v-application--wrap>div {
	height: 100%;
}
.no-gutters>.col .v-card.v-sheet.theme--light {
	height: 100%;
}
.col .v-card.v-sheet.theme--light .row {
	height: 30%;
}
.col .v-card.v-sheet.theme--light .row .v-toolbar__content {
	height: 100% !important;
}
.v-application .text-center {
	height: 20%;
}
.v-footer.white.v-sheet.v-sheet--tile.theme--light.v-footer--absolute {
	height: 50% !important;
}
.v-footer.white.v-sheet.v-sheet--tile.theme--light.v-footer--absolute .row {
	height: 100%;
}
.v-footer.white.v-sheet.v-sheet--tile.theme--light.v-footer--absolute .row .v-progress-linear.v-progress-linear--rounded.theme--light {
	height: 100% !important;
}
.v-responsive__content {
	height: 0;
}
.v-responsive {
	height: 0;
}
.time {
	font-size: 2.5vw;
	color: #f4fc03;
	text-align: center;
}
.f_mname {
	font-size: 2vw;
	color: #333;
}
.f_p {
	font-size: 1.5vw;
	color: #333;
}
.vt {
	font-size: 2vw;
	color: #ffffff;
}
.f_end {
	font-size: 2vw;
	height: 100%;
	display: flex;
	align-items: center;
	justify-content: center;
}
.v-footer--absolute {
	position: relative;
}
.v-footer.white.v-sheet.v-sheet--tile.theme--light.v-footer--absolute {
	width: 100%;
	margin: 0;
	padding: 0;
}
.v-card.v-sheet.theme--light .row {
	margin:0;
}
.no-gutters>.col {
	flex: 0 33%;
	height: 44%;
	min-height: 44%;
}
.no-gutters .col:nth-child(3n) {
	margin:0 0.5%;
}
.v-toolbar--dense .v-toolbar__content, .v-toolbar--dense .v-toolbar__extension {
	height: 100% !important;
}
.theme--light.v-toolbar.v-sheet {
	height: 100% !important;
}
.no-gutters > div:nth-child(4) .v-progress-linear__determinate {
	background-color: #FF0000 !important;
}
.no-gutters > div:nth-child(5) .v-progress-linear__determinate {
	background-color: #FF5E00 !important;
}
.no-gutters > div:nth-child(6) .v-progress-linear__determinate {
	background-color: #FF5E00 !important;
}
.no-gutters > div:nth-child(7) .v-progress-linear__determinate {
	background-color: #FF0000 !important;
}
.no-gutters > div:nth-child(8) .v-progress-linear__determinate {
	background-color: #FF5E00 !important;
}
/* PC */
@media all and ( min-width:1024px ) and ( max-width:1920px ) {
	body {
		font-size: 18px;
	}
}
/* Tablet */
@media all and ( min-width:768px ) and ( max-width:1023px ) {
	body {
		font-size: 13px;
	}
	.v-toolbar__content {
		padding: 4px 12px;
	}
	.time {
		font-size: 1.5em;
		color: #f4fc03;
		text-align: center;
	}
	.f_mname {
		font-size: 1.5em;
		color: #333;
	}
	.f_p {
		font-size: 1em;
		color: #333;
	}
	.vt {
		font-size: 1.3em;
		color: #ffffff;
	}
	.f_end {
		font-size: 1.2em;
	}
}
/* mobile */
@media all and ( max-width:767px ) {
	.no-gutters>.col {
		flex: auto;
		margin-bottom: 1% !important;
	}
	.time {
		font-size: 1.5em;
		color: #f4fc03;
		text-align: center;
	}
	.f_mname {
		font-size: 1.5em;
		color: #333;
	}
	.f_p {
		font-size: 1em;
		color: #333;
	}
	.vt {
		font-size: 1.3em;
		color: #ffffff;
	}
	.f_end {
		font-size: 1.2em;
	}
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
	          
	        },
	        {
	          mid : 'PumaV400',
	          idx : 2,
	          process : 'O0229',
	          timer : '04:34',
	          count : '4/100',
	          fTime : '84 시간 40 분',
	          
	        },
	        {
	          mid : 'Lynx220C',
	          idx : 3,
	          process : 'D580007-02-F',
	          timer : '01:33',
	          count : '459/500',
	          fTime : '2 시간 36 분',
	          
	        },
	        {
	          mid : 'Puma240',
	          idx : 4,
	          process : 'WGR150D35H24-02-1',
	          timer : '00:10',
	          count : '70/100',
	          fTime : '1 시간 31 분',
	          
	        },
	        {
	          mid : 'Lynx220CL',
	          idx : 5,
	          process : 'CS98D25H49-02-02',
	          timer : '02:34',
	          count : '12/100',
	          fTime : '5 시간 0 분',
	          
	        },
	        {
	          mid : 'Lynx220SY',
	          idx : 6,
	          process : 'JIG-CD',
	          timer : 'READY',
	          count : '110/200',
	          fTime : '23 시간 48 분',
	          
	        },
	      ],
	    }
	  },
	})
<!-- JS 끝 !-->
</script>