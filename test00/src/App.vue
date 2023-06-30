<template>
  <div>
    <button @click="handletest">计算</button>
  </div>
</template>
<script>
export default {
  data () {
    return {
      words: 'Since 2016, this leading Philippine fiber broadband operator has built or leased nineIDCs across Manila’s metropolitan area, a region with 12.9 million people and one ofthe most densely populated cities in the world.The demand for data center services hasdramatically increased so much that Converge is already engaging in a new series ofmajor upgrades.As the company’s IDC services have been growing, customer demand hasgrown even faster, with bandwidth demand increasing ten- fold in just two years,straining legacy DCI systems.But given physical constraints, any new upgrades neededto be carefully thought through.The physical footprint had to be kept to a minimum,with hardware future - proofed to be match predicted increases in bandwidth demand.Furthermore, rollout needed to be quick and efficient, and simplified Operations andMaintenance(O & M) were a must, to minimize the risk of downtime.Converge looked toimplement upgrades that could be deployed quickly in order to maintain the company’sreputation for high - speed, low latency services and network reliability.Following anin -depth evaluation, it selected Huawei’s DC OptiX 2.0 Wavelength Division Multiplexing(WDM) solution that, Brusola believes, is capable of handling the company’s burgeoningIDC traffic not just right now, but for the next decade too'
    }
  },
  methods: {
    handletest () {
      const arr = this.words.split('.')
      const arr1 = []
      const arr2 = []
      let newArr = []
      for (let i = 0; i < arr.length; i++) {
        arr1.push(arr[i].split(','))
        for (let j = 0; j < arr[i].split(',').length; j++) {
          arr2.push(arr1[i][j].split(' '))
        }
      }
      newArr = arr2.flat(Infinity)
      newArr.pop(newArr.length)

      let times = 0
      const resultArr = []
      const timesArr = []
      for (let i = 0; i < newArr.length; i++) {
        for (let j = 0; j < newArr.length; j++) {
          if (newArr[i] === newArr[j]) {
            times += 1
          }
        }
        timesArr.push(times)
        times = 0
      }
      timesArr.sort(function (a, b) { return b - a })
      newArr.sort()
      for (let i = 0; i < timesArr.length; i++) {
        resultArr.push(timesArr[i] * newArr[i].length)
        // console.log(newArr[i] + '出现了' + timesArr[i] + '次')
        console.log(newArr[i] + '出现了' + timesArr[i] + '次' + 'left:' + newArr[i - 1] + ':' + timesArr[i - 1] + '次' + 'right:' + newArr[i + 1] + ':' + timesArr[i + 1] + '次')
      }
      for (let i = 0; i < 3; i++) {
        console.log(newArr[i] + '出现了' + timesArr[i] + '次' + 'left:' + newArr[i - 1] + ':' + timesArr[i - 1] + '次' + 'right:' + newArr[i + 1] + ':' + timesArr[i + 1] + '次')
      }
      // console.log(newArr)
      // console.log(timesArr)
      // console.log(newArr[a])
      // console.log(timesArr[a])
    }
  }
}
</script>
