<template>
    <app-layout title="View Photo">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">View Photo</h2>
        </template>
        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <div class="grid grid-cols-2">
                    <img :src="'/storage/' + photo.path" alt />
                        <div class="mt-1 flex justify-left px-6 pt-5 pb-6 border-gray-300 border-solid rounded-md">    
                                <p>
                                    {{ photo.description }}
                                </p>
                        </div>
                </div>
            </div>
        </div>
    </app-layout>
</template>

<script>
import { defineComponent } from "vue";
import AppLayout from "@/Layouts/AppLayout.vue";
import { useForm } from '@inertiajs/inertia-vue3';

export default defineComponent({
    components: {
        AppLayout,
    },
    props: {
        photo: Object
    },
    setup(props) {
        const form = useForm({
            _method: "PUT",
            path: null,
            description: props.photo.description,
        })

        return { form }
    },

});</script>