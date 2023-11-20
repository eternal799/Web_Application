<template>
    <ContentBase>
        <div class="row">
            <div class="col-3">
                <UserProfileInfo @follow123="follow" @unfollow1234="unfollow" v-bind:user="user"></UserProfileInfo>
                <UserProfileWrite @post_post_123="post_a_post"></UserProfileWrite>
            </div>
            <div class="col-9">
                <UserProfilePosts :posts="posts"></UserProfilePosts>
            </div>
        </div>
    </ContentBase>
</template>
  
<script>

import ContentBase from '../components/ContentBase';
import UserProfileInfo from '../components/UserProfileInfo';
import UserProfilePosts from '../components/UserProfilePosts'
import UserProfileWrite from '../components/UserProfileWrite';
import { reactive } from 'vue'

export default {
    name: 'UserProfileView',
    components: {
        ContentBase,
        UserProfileInfo,
        UserProfilePosts,
        UserProfileWrite
    },
    setup() {
        const user = reactive({
            username: "wanghuadan",
            lastName: "Wang",
            firstName: "HuaDan",
            followerCount: 100,
            is_followed: false
        })

        const posts = reactive({
            count: 4,
            posts: [
                {
                    id: 1,
                    userId: 1,
                    content: "今天上了Web课"
                },
                {
                    id: 2,
                    userId: 1,
                    content: "今天上了Web课"
                },
                {
                    id: 3,
                    userId: 1,
                    content: "今天上了Web课"
                },
                {
                    id: 4,
                    userId: 1,
                    content: "今天上了Web课"
                },
            ]
        })
        const follow = () => {
            if (user.is_followed) {
                return
            }
            user.is_followed = true
            user.followerCount++
        }

        const unfollow = () => {
            if (!user.is_followed) {
                return
            }
            user.is_followed = false
            user.followerCount--
        }

        const post_a_post = (content) => {
            posts.count++
            posts.posts.unshift({
                id: posts.count,
                userId: 1,
                content: content
            })

        }

        return {
            user,
            follow,
            unfollow,
            posts,
            post_a_post
        }
    }
}
</script>
  
<style scoped></style>