<template>
    <div class="p-2 w-full lg:w-72">
        <div class="flex flex-col space-y-4 items-start">
            <div class="text-lg font-bold">Table Of Contents</div>

            <ul class="px-2 space-y-4 text-sm">
                <li v-for="item in content" :key="item.id" class="space-y-4">
                    <a
                        :href="`#${item.id}`"
                        class="text-zinc-800 dark:text-royal-yellow text-sm lg:text-base"
                        >{{ item.text }}</a
                    >
                    <ul v-if="item.children" class="space-y-4 ml-4">
                        <li
                            v-for="nestedItem in item.children"
                            :key="nestedItem.id"
                        >
                            <a
                                :href="`#${nestedItem.id}`"
                                class="text-zinc-800 dark:text-royal-yellow text-xs lg:text-sm"
                                >{{ nestedItem.text }}</a
                            >
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
    </div>
</template>
<script setup>
    const { content } = defineProps(["content"]);
    //  console.log(content)
</script>
