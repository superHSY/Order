<template>
	<div>
		<el-card>
			<div id="main" style="width:100%;height:500px;"></div>
		<el-row>
			<el-link href="https://element.eleme.io" target="_blank">继续使用</el-link>
		</el-row>
		</el-card>
		
	</div>
</template>

<script>
let echarts = require('echarts');
export default {
	data() {
		return {

		}
	},
	created() {},
	mounted() {
		var myChart = echarts.init(document.getElementById('main'));

		 var option = {
              title: {
        text: '使用情况',
        subtext: '纯属虚构',
        left: 'center'
    },
    tooltip: {
        trigger: 'item',
        formatter: '{a} <br/>{b} : {c} ({d}%)'
    },
    legend: {
        left: 'center',
        top: 'bottom',
        data: ['rose1', 'rose2', 'rose3', 'rose4', 'rose5', 'rose6', 'rose7', 'rose8']
    },
    toolbox: {
        show: true,
        feature: {
            mark: {show: true},
            dataView: {show: true, readOnly: false},
            restore: {show: true},
            saveAsImage: {show: true}
        }
    },
    series: [
        {
            name: '半径模式',
            type: 'pie',
            radius: [20, 140],
            center: ['25%', '50%'],
            roseType: 'radius',
            itemStyle: {
                borderRadius: 5
            },
            label: {
                show: false
            },
            emphasis: {
                label: {
                    show: true
                }
            },
            data: [
                {value: 40, name: 'rose 1'},
                {value: 33, name: 'rose 2'},
                {value: 28, name: 'rose 3'},
                {value: 22, name: 'rose 4'},
                {value: 20, name: 'rose 5'},
                {value: 15, name: 'rose 6'},
                {value: 12, name: 'rose 7'},
                {value: 10, name: 'rose 8'}
            ]
        },
        {
            name: '面积模式',
            type: 'pie',
            radius: [20, 140],
            center: ['75%', '50%'],
            roseType: 'area',
            itemStyle: {
                borderRadius: 5
            },
            data: [
                {value: 30, name: 'rose 1'},
                {value: 28, name: 'rose 2'},
                {value: 26, name: 'rose 3'},
                {value: 24, name: 'rose 4'},
                {value: 22, name: 'rose 5'},
                {value: 20, name: 'rose 6'},
                {value: 18, name: 'rose 7'},
                {value: 16, name: 'rose 8'}
            ]
        }
    ]
        };
		myChart.setOption(option);
	},
	methods: {

	}
}
</script>

<style lang="less" scoped>
.el-row {
	font-family:Microsoft JhengHei;
	text-align: center;
	font-size: 25px;
}
</style>