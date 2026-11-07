<template>
    <main class="recolor-page">
        <section class="recolor-layout">
            <div class="editor">
                <header class="page-header">
                    <h1>Recolor it like magic</h1>
                    <p>
                        Upload an image, name the object you want to recolor,
                        then choose a new color
                    </p>
                </header>

                <div class="editor-row">
                     <div class="upload-column">
                        <label class="field-label" for="image-upload">
                            Upload image
                        </label>

                        <label class="image-upload" for="image-upload">
                            <img
                                :src="imageUrl || sampleImageUrl1"
                                :alt="imageUrl ? 'Uploaded image' : 'Sample image'"
                            />
                            <span class="upload-action" aria-hidden="true">↻</span>
                        </label>

                        <input
                            id="image-upload"
                            class="visually-hidden"
                            type="file"
                            accept="image/*"
                            @change="handleUpload"
                        />
                    </div>

                    <div class="controls-column">
                        <label class="field-label" for="object-name">
                            Name the object to recolor
                        </label>
                        <textarea
                            id="object-name"
                            v-model="objectName"
                            class="object-input"
                            placeholder="e.g. Shirt"
                        ></textarea>

                        <label class="field-label color-label" for="color-hex">
                            Choose a new color
                        </label>
                        <div class="color-input">
                            <span>#</span>
                            <input
                                id="color-hex"
                                v-model="hexColor"
                                type="text"
                                maxlength="6"
                                aria-label="Hex color"
                            />
                            <input
                                v-model="color"
                                class="color-swatch"
                                type="color"
                                aria-label="Choose color"
                                @input="syncHex"
                            />
                        </div>

                        <button
                            class="generate-button"
                            type="button"
                            :disabled="!imageUrl || !objectName.trim()"
                            @click="
                                $emit('generate', {
                                    image: selectedFile,
                                    objectName,
                                    color,
                                })
                            "
                        >
                            Generate
                        </button>
                    </div>

                    <div class="arrow" aria-hidden="true">→</div>

                    <div class="preview-column">
                        <div class="preview-frame">
                            <img
                                :src="previewUrl || sampleImageUrl2"
                                :alt="
                                    previewUrl
                                        ? 'Recolored preview'
                                        : 'Sample image preview'
                                "
                            />
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>
</template>

<script>
export default {
    name: "RecolorTool",

    emits: ["generate"],

    data() {
        return {
            selectedFile: null,
            imageUrl: "",
            previewUrl: "",
            sampleImageUrl1: "/images/Bikes/Recolor/one.png",
            sampleImageUrl2: "/images/Bikes/Recolor/two.png",
            objectName: "Shirt",
            color: "#2F5DFF",
            hexColor: "2F5DFF",
        };
    },

    watch: {
        hexColor(value) {
            const normalized = value.replace("#", "");

            if (/^[0-9a-fA-F]{6}$/.test(normalized)) {
                this.color = `#${normalized}`;
            }
        },
    },

    methods: {
        handleUpload(event) {
            const file = event.target.files?.[0];
            if (!file) return;

            if (this.imageUrl) {
                URL.revokeObjectURL(this.imageUrl);
            }

            this.selectedFile = file;
            this.imageUrl = URL.createObjectURL(file);
            this.previewUrl = "";
        },

        syncHex() {
            this.hexColor = this.color.replace("#", "").toUpperCase();
        },
    },

    beforeUnmount() {
        if (this.imageUrl) {
            URL.revokeObjectURL(this.imageUrl);
        }
    },
};
</script>

<style scoped>
.recolor-page {
    min-height: 100vh;
    display: grid;
    place-items: center;
    padding: 56px 32px;
    color: #202326;
    background: radial-gradient(
            ellipse at 18% 18%,
            rgba(167, 202, 173, 0.7),
            transparent 33%
        ),
        radial-gradient(
            ellipse at 78% 15%,
            rgba(219, 187, 191, 0.62),
            transparent 35%
        ),
        radial-gradient(
            ellipse at 43% 76%,
            rgba(224, 208, 169, 0.7),
            transparent 38%
        ),
        #d9ded9;
}

.recolor-layout {
    width: min(100%, 1320px);
}

.editor {
    width: 100%;
}

.page-header {
    margin-bottom: 18px;
}

.page-header h1 {
    margin: 0 0 7px;
    font-size: clamp(1.8rem, 3vw, 2rem);
    line-height: 1.15;
    letter-spacing: -0.04em;
}

.page-header p {
    margin: 0;
    color: #4c5152;
    font-size: 0.92rem;
}

.editor-row {
    display: grid;
    grid-template-columns: 196px minmax(250px, 288px) 40px minmax(380px, 548px);
    align-items: center;
    gap: 32px;
}

.field-label {
    display: block;
    margin-bottom: 12px;
    color: #454a4b;
    font-size: 0.78rem;
}

.image-upload {
    position: relative;
    display: grid;
    width: 100%;
    aspect-ratio: 1 / 1;
    overflow: hidden;
    place-items: center;
    border-radius: 9px;
    background: rgba(77, 119, 137, 0.68);
    cursor: pointer;
}

.image-upload img,
.preview-frame img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.upload-placeholder {
    padding: 16px;
    color: white;
    font-size: 0.85rem;
}

.upload-action {
    position: absolute;
    top: 50%;
    left: 50%;
    display: grid;
    width: 40px;
    height: 40px;
    place-items: center;
    transform: translate(-50%, -50%);
    border-radius: 9px;
    background: #fff7f2;
    color: #303536;
    font-size: 1.35rem;
}

.visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    clip-path: inset(50%);
}

.object-input {
    display: block;
    width: 100%;
    height: 70px;
    resize: vertical;
    padding: 11px;
    border: 1px solid rgba(60, 65, 68, 0.18);
    border-radius: 9px;
    outline: none;
    background: rgba(255, 255, 255, 0.94);
    color: #303536;
    font: inherit;
    font-size: 0.82rem;
}

.object-input:focus,
.color-input:focus-within {
    border-color: #647dff;
}

.color-label {
    margin-top: 13px;
    margin-bottom: 8px;
}

.color-input {
    display: flex;
    height: 32px;
    align-items: center;
    gap: 6px;
    padding: 0 7px 0 14px;
    border: 1px solid rgba(60, 65, 68, 0.12);
    border-radius: 8px;
    background: rgba(255, 255, 255, 0.94);
    color: #767a7b;
    font-size: 0.8rem;
}

.color-input input[type="text"] {
    flex: 1;
    min-width: 0;
    border: 0;
    outline: 0;
    background: transparent;
    color: #555a5b;
    font: inherit;
}

.color-swatch {
    width: 21px;
    height: 21px;
    padding: 0;
    overflow: hidden;
    border: 0;
    border-radius: 3px;
    background: transparent;
    cursor: pointer;
}

.color-swatch::-webkit-color-swatch-wrapper {
    padding: 0;
}

.color-swatch::-webkit-color-swatch {
    border: 0;
    border-radius: 3px;
}

.generate-button {
    display: block;
    margin: 11px 0 0 auto;
    padding: 8px 17px;
    border: 0;
    border-radius: 8px;
    background: #345cff;
    color: #fff;
    font: inherit;
    font-size: 0.78rem;
    font-weight: 600;
    cursor: pointer;
}

.generate-button:disabled {
    opacity: 0.55;
    cursor: not-allowed;
}

.arrow {
    text-align: center;
    font-size: 1.7rem;
}

.preview-frame {
    width: 100%;
    aspect-ratio: 548 / 308;
    overflow: hidden;
    border-radius: 12px;
    background: rgba(55, 110, 137, 0.7);
    box-shadow: 0 18px 35px rgba(40, 49, 51, 0.18);
}

.preview-frame img {
    display: block;
}

@media (max-width: 1000px) {
    .editor-row {
        grid-template-columns: minmax(150px, 0.8fr) minmax(220px, 1.2fr);
        gap: 24px;
    }

    .arrow {
        display: none;
    }

    .preview-column {
        grid-column: 1 / -1;
    }
}

@media (max-width: 600px) {
    .recolor-page {
        padding: 36px 20px;
    }

    .editor-row {
        grid-template-columns: 1fr;
        gap: 20px;
    }

    .upload-column {
        width: min(100%, 260px);
    }

    .preview-column {
        grid-column: auto;
    }
}
</style>
