<script setup lang="ts">
import { computed } from "vue"
import { RouterLink } from "vue-router"
import type { Member } from "@/interfaces"
import { useMembersStore } from "@/stores/members"

const membersStore = useMembersStore()
membersStore.prepareMemberList()

const memberList = computed(
    (): Map<number, Member> => {
        return membersStore.memberList;
    }
)
const isEmptyList = computed(
    (): boolean => {
        return membersStore.isMemberListEmpty
    }
)
const isLoading = computed(
    (): boolean => {
        return membersStore.isLoading
    }
)
</script>

<template>
    <h1>会員管理</h1>
    <nav id="breadcrumbs">
        <ul>
            <li>
                <RouterLink :to="{name: 'AppTop'}">
                    Top
                </RouterLink>
            </li>
            <li>会員リスト</li>
        </ul>
    </nav>

    <section>
        <h2>会員リスト</h2>
        <p>
            新規登録は<RouterLink :to="{name : 'MemberAdd'}">こちら</RouterLink>から
        </p>
        <p v-if="isLoading">データを取得中...</p>
        <section>
            <ul>
                <li v-if="isEmptyList">会員情報は存在しません。</li>
                <li v-for="[id, member] in memberList" :key="id">
                    <RouterLink :to="{name : 'MemberDetail', params: {id: id}}">
                        IDが{{ id }}の{{ member.name }}さん
                    </RouterLink>
                </li>
            </ul>
        </section>
        <RouterView/>
    </section>
</template>