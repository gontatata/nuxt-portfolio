<template>
    <!-- ブラウザで表示するコード -->
    <!-- divでテンプレート内の親要素を一つに。 -->
    <div>
        <!-- template内でデータを表示させるには{{  }}を使う -->
        <div v-for="singleData in data" :key="singleData.id">
        {{ singleData.date }}
        <!-- <br>
        {{ singleData.date }} -->
        
        </div>
    </div>
</template>

<script setup>
    // データの取得や操作などの処理
    const { data } = await useAsyncData("blogQuery",() =>
    queryContent("/blog").find()
    )
</script>
