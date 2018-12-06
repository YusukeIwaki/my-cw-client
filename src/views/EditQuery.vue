<template>
  <v-app>
    <v-toolbar app>
      <v-btn to="/" icon>
        <v-icon>arrow_back</v-icon>
      </v-btn>
      <v-toolbar-title>検索</v-toolbar-title>
    </v-toolbar>
    <v-content app>
      <v-container>
        <v-text-field
          label="キーワード"
          v-model="keyword"/>
        <v-text-field
          label="除外キーワード"
          v-model="excludedKeyword"/>
        <v-select
          :items="paymentTypeItems"
          item-text="label"
          item-value="value"
          v-model="paymentTypes"
          label="仕事の形式"
          multiple
        ></v-select>

        <ul>
        <li v-if="keyword">+{{ keyword }}</li>
        <li v-if="excludedKeyword">-{{ excludedKeyword }}</li>
        <li>x{{ paymentTypes }}</li>
        </ul>
        <v-spacer />
        <v-btn block color="primary">検索</v-btn>
      </v-container>
    </v-content>
  </v-app>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator'

@Component({
})
export default class EditQuery extends Vue {
    paymentTypeItems = [
      { label: "固定報酬", value: "fixed_price" },
      { label: "時間単価", value: "hourly" },
      { label: "コンペ", value: "competition" },
      { label: "タスク", value: "task" }
    ];

    keyword: string = "";
    excludedKeyword: string = "";
    paymentTypes: Array<string> = [];
}
</script>
