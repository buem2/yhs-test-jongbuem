<!-- HTML 시작 !-->
<div id="app">
	<v-app id="inspire">
	    <div>
			<v-row no-gutters>
				<v-card color="black" width="100%">
				  <div style='text-align:center'>
					<span class="time">2020-03-14</span>
				  </div>
				</v-card>
				<v-responsive width="100%"></v-responsive>
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
							  <span class="f_end" style="align:center">{{item.timer}}</span>
							</div>
							<v-footer :fixed="true" height="100" absolute class="white">
							  <v-row>
								<v-progress-linear value="15" height="100"
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
}
.v-sheet.v-sheet--tile.theme--light.v-toolbar.v-toolbar--dense.v-toolbar--flat {
	height: 120px !important;
}

.v-toolbar__content {
	height: 120px !important;
}

.v-footer--absolute {
	position: static;
}
.v-application .text-center {
	height: 90px;
	line-height: 90px;
}
.v-footer.white.v-sheet.v-sheet--tile.theme--light.v-footer--absolute {
	width: 100%;
	margin: 0;
	padding: 0;
	height: 140px !important;
}
.v-progress-linear.v-progress-linear--rounded.theme--light {
	height: 140px !important;
}
.v-card.v-sheet.theme--light .row {
	margin:0;
}

.no-gutters>.col {
	flex: 0 33%;
	margin-bottom: 0.5%;
}
.no-gutters .col:nth-child(3n+1) {
	margin:0 0.5%;
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
	.v-sheet.v-sheet--tile.theme--light.v-toolbar.v-toolbar--dense.v-toolbar--flat {
		height: 85px !important;
	}
	.v-toolbar__content {
		height: 85px !important;
	}
	.v-application .text-center {
		height: 60px;
		line-height: 60px;
	}
	.v-footer.white.v-sheet.v-sheet--tile.theme--light.v-footer--absolute {
		height: 100px !important;
	}
	.v-progress-linear.v-progress-linear--rounded.theme--light {
		height: 100px !important;
	}

}



/* Tablet */
@media all and ( min-width:768px ) and ( max-width:1023px ) {
	.v-sheet.v-sheet--tile.theme--light.v-toolbar.v-toolbar--dense.v-toolbar--flat {
		height: 70px !important;
	}

	.v-toolbar__content {
		height: 70px !important;
	}
	.v-application .text-center {
		height: 50px;
		line-height: 50px;
	}
	.v-footer.white.v-sheet.v-sheet--tile.theme--light.v-footer--absolute {
		height: 100px !important;
	}
	.v-progress-linear.v-progress-linear--rounded.theme--light {
		height: 100px !important;
	}

}



/* mobile 2 */
@media all and ( max-width:767px ) {
	.no-gutters>.col {
		flex: auto;
		margin-bottom: 10px !important;
	}
	.time {
		font-size: 2.5vw;
	}
	.f_mname {
		font-size: 5vw;
	}
	.f_p {
		font-size: 4vw;
	}
	.vt {
		font-size: 4.5vw;
	}
	.f_end {
		font-size: 3.5vw;
	}
	.v-sheet.v-sheet--tile.theme--light.v-toolbar.v-toolbar--dense.v-toolbar--flat {
		height: 60px !important;
	}

	.v-toolbar__content {
		height: 60px !important;
	}
	.v-application .text-center {
		height: 40px;
		line-height: 40px;
	}
	.v-footer.white.v-sheet.v-sheet--tile.theme--light.v-footer--absolute {
		height: 80px !important;
	}
	.v-progress-linear.v-progress-linear--rounded.theme--light {
		height: 80px !important;
	}
}


/* mobile 1 */
@media all and ( max-width:480px ) {
	.f_mname {
		font-size: 6vw;
	}
	.v-application .text-center {
		height: 30px;
		line-height: 30px;
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