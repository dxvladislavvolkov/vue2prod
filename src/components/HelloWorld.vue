<template>
  <div class="hello">
    <form v-on:submit.prevent="onFormSubmit">
      <dx-form
        ref="form"
        label-location="top"
        :form-data="state"
        :show-colon-after-label="false"
      >
        <dx-group-item caption="Sign In">
          <dx-simple-item
            data-field="firstName"
            editor-type="dxTextBox"
            :editor-options="{ readOnly: readonly }"
          >
            <dx-label text="First Name" />
            <dx-required-rule v-if="!readonly" />
          </dx-simple-item>
        </dx-group-item>

        <dx-button-item horizontal-alignment="center">
          <dx-button-options
            text="save"
            type="success"
            :use-submit-behavior="true"
          />
        </dx-button-item>
      </dx-form>
    </form>
  </div>
</template>

<script>
import {
  DxForm,
  DxSimpleItem,
  DxGroupItem,
  DxButtonItem,
  DxButtonOptions,
  DxRequiredRule,
  DxLabel,
} from "devextreme-vue/form";
export default {
  name: 'HelloWorld',
  components: {
    DxForm,
  DxSimpleItem,
  DxGroupItem,
  DxButtonItem,
  DxButtonOptions,
  DxRequiredRule,
  DxLabel,
  },
  data() {
    return {
      state: {}
    }
  },
  props: {
    readonly: {
      type: Boolean,
      default: false
    },
  },
  methods: {
    onFormSubmit() {}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
