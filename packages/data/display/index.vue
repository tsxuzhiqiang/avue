<template>
  <div class="avue-data-display">
    <el-row :span="24">
      <el-col v-for="(item,index) in data"
              :key="index"
              :md="span"
              :xs="12"
              :sm="12">
        <div class="item"
             :style="{color:color}">
          <a :href="item.href"
             @click="item.click&&item.click(item)"
             :target="item.target">
            <avue-count-up :animation="item.animation || animation"
                           :decimals="item.decimals || decimals"
                           class="count"
                           :style="{color:item.color}"
                           :end="item.count"></avue-count-up>
            <span class="splitLine" />
            <div class="title"
                 :style="{color:item.fontColor}">{{item.title}}</div>
          </a>
        </div>
      </el-col>
    </el-row>

  </div>
</template>

<script>
import create from "core/create";
export default create({
  name: "data-display",
  data () {
    return {};
  },
  computed: {
    animation () {
      return this.option.animation
    },
    decimals () {
      return this.option.decimals || 0
    },
    span () {
      return this.option.span || 6;
    },
    data () {
      return this.option.data || [];
    },
    color () {
      return this.option.color || "rgb(63, 161, 255)";
    }
  },
  props: {
    option: {
      type: Object,
      default: () => { }
    }
  },
  created () { },
  methods: {}
});
</script>
