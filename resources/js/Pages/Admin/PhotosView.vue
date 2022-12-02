<template>
    <app-layout title="View Photo">
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 leading-tight">View Photo</h2>
        </template>
        <div class="py-12">
            <div class="max-w-7xl mx-auto sm:px-6 lg:px-8">
                <h1>Photo</h1>
                <section class="photos">
                    <div class="preview p-4">
                            <img :src="'/storage/' + photo.path" alt />
                            <br>
                            <p>
                                {{ photo.description }}
                            </p>

                        </div>
                </section>
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