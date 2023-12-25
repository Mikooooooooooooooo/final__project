<template>
    <div
        class="email-item"
        style="gap: 20px; padding: 20px; border-bottom: 1px solid gray"
    >
        <div
            style="
                display: flex;
                align-items: center;
                height: 50px;
                width: 20px;
            "
        >
            <label class="checkbox">
                <input type="checkbox" />
                <span class="checkmark"></span>
            </label>
        </div>
        <div class="flex" style="gap: 20px">
            <div
                @click="changeActive"
                style="
                    width: 50px;
                    height: 50px;
                    display: flex;
                    align-items: center;
                    justify-content: center;
                    cursor: pointer;
                "
                :style="
                    isActive
                        ? 'background-color: #f9efd7'
                        : 'background-color: #f5f5f5'
                "
            >
                <img
                    class=""
                    style="width: 25px; height: 25px"
                    :src="
                        isActive
                            ? '../assets/star.svg'
                            : '../assets/star-gray.svg'
                    "
                    alt="star"
                />
            </div>
            <img class="avatar" :src="email.avatar" alt="Sender's Avatar" />
        </div>
        <div class="main-box-email" style="width: 600px">
            <div class="flex" style="gap: 10px">
                <div class="email">{{ email.address }}</div>
                <div class="email-time">{{ email.timeAgo }}</div>
            </div>

            <div class="email-content" style="font-weight: 600">
                <div class="subject">{{ email.subject }}</div>
            </div>
            <div style="font-size: 12px">
                <div class="preview">{{ email.preview }}</div>
            </div>
            <div class="attachments">
                <div
                    class="attachment"
                    v-for="file in email.attachments.slice(0, 2)"
                    :key="file.name"
                >
                    <img
                        :src="getIconForFileType(file.type)"
                        :alt="file.name"
                    />
                    <div class="filename">{{ file.name }}</div>
                </div>
                <div
                    v-if="email.attachments.length > 2"
                    class="more-files attachment"
                >
                    {{ email.attachments.length - 2 }} files more
                </div>
            </div>
        </div>
        <div
            style="
                display: flex;
                flex-direction: column;
                align-items: end;
                gap: 40px;
            "
        >
            <img
                src="../../assets/dots.svg"
                style="transform: rotate(90deg)"
                alt=""
            />
            <div class="flex" style="gap: 10px; align-items: center">
                <img
                    style="
                        padding: 8px;
                        background-color: #fbeeeb;
                        width: 40px;
                        height: 40px;
                    "
                    src='../../assets/print.svg'
                    alt=""
                />
                <img src="../../assets/time.svg" alt="" />
                <img src="../../assets/attach.svg" alt="" />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "EmailItem",
    props: {
        email: {
            type: Object,
            required: true,
        },
    },
    data() {
        return {
            isActive: true,
        };
    },
    computed: {},
    methods: {
        getIconForFileType(fileType) {
            if (fileType == "fig") {
                return "../../assets/gallery.svg";
            }
            return "../../assets/file.svg" ; 
        },
        changeActive() {
            this.isActive = !this.isActive;
        },
    },
};
</script>

<style scoped>
.email-item {
    display: flex;
}

.main-box-email {
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.sender-info {
    display: flex;
    align-items: center;
}

.avatar {
    width: 50px;
    height: 50px;
}

.meta-info {
    display: flex;
    flex-direction: column;
}

.star-icon {
}

.email {
    color: #bcb4c4;
    font-size: 12px;
}

.email-time {
    color: #bcb4c4;
    font-size: 12px;
}

.email-content {
}

.attachments {
    display: flex;
    gap: 20px;
    color: #ef6e4d;
    font-size: 12px;
}

.attachment {
    display: flex;
    align-items: center;
    border: 1px solid #f0edec;
    padding: 10px 20px;
    gap: 10px;
}

.filename {
}

.more-files {
    background-color: #fbeeeb;
}
</style>
