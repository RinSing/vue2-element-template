<script>
export default {
  name: "item",
  functional: true,
  props: {
    icon: {
      type: String,
      default: "",
    },
    title: {
      type: String,
      default: "",
    },
  },
  render(h, context) {
    const { icon, title } = context.props;
    const vnodes = [];
    if (icon) {
      if (icon.includes("el-icon")) {
        vnodes.push(<i class={[icon, "sub-el-icon"]} />);
      } else {
        vnodes.push(<icon-svg type={icon} />);
        //vnodes.push(<svg-icon icon-class={icon} />);
      }
    }
    if (title) {
      vnodes.push(<span slot="title">{title}</span>);
    }

    return vnodes;
  },
};
</script>

<style scoped>
.sub-el-icon {
  color: currentColor;
  width: 1em !important;
  height: 1em;
}
</style>
