<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Graysen</title>
<style>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
:root {
    --background: #f3ecdf;
    --card: #fffaf1;
    --text: #171717;
    --green: #356b4f;
    --green-dark: #244d39;
    --border: #d9cfbf;
}
body {
    font-family: Arial, Helvetica, sans-serif;
    background: var(--background);
    color: var(--text);
    min-height: 100vh;
}
header {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(243,236,223,0.95);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid var(--border);
}
.nav {
    max-width: 1150px;
    margin: auto;
    padding: 18px 22px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}
.logo {
    font-size: 28px;
    font-weight: 700;
    letter-spacing: -1px;
}
nav {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
}
nav button {
    border: none;
    background: transparent;
    color: var(--text);
    padding: 10px 13px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 14px;
}
nav button:hover,
nav button.active {
    background: var(--green);
    color: white;
}
main {
    max-width: 1150px;
    margin: auto;
    padding: 55px 22px 80px;
}
.page {
    display: none;
    animation: fade .25s ease;
}
.page.active {
    display: block;
}
@keyframes fade {
    from {
        opacity: 0;
        transform: translateY(8px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
.hero {
    min-height: 65vh;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 50px;
}
.hero-text {
    max-width: 680px;
}
.eyebrow {
    color: var(--green);
    text-transform: uppercase;
    letter-spacing: 3px;
    font-size: 12px;
    font-weight: bold;
    margin-bottom: 18px;
}
h1 {
    font-size: clamp(52px, 9vw, 105px);
    line-height: .9;
    letter-spacing: -6px;
    margin-bottom: 28px;
}
.hero p {
    font-size: 19px;
    line-height: 1.7;
    max-width: 650px;
}
.hero-card {
    width: 280px;
    min-width: 280px;
    height: 350px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 20px;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
}
.hero-card img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.placeholder {
    color: #81796d;
    text-align: center;
    padding: 25px;
}
.button {
    display: inline-block;
    border: none;
    background: var(--green);
    color: white;
    padding: 13px 18px;
    border-radius: 9px;
    cursor: pointer;
    font-weight: 600;
    margin-top: 25px;
}
.button:hover {
    background: var(--green-dark);
}
.secondary {
    background: transparent;
    color: var(--text);
    border: 1px solid var(--border);
}
.secondary:hover {
    background: var(--card);
    color: var(--text);
}
.section-title {
    font-size: 48px;
    letter-spacing: -2px;
    margin-bottom: 10px;
}
.section-description {
    color: #655f56;
    line-height: 1.7;
    margin-bottom: 35px;
    max-width: 700px;
}
.photo-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 16px;
}
.photo-item {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    overflow: hidden;
}
.photo-item img {
    width: 100%;
    aspect-ratio: 1 / 1;
    object-fit: cover;
    display: block;
    cursor: pointer;
}
.photo-caption {
    padding: 12px;
    font-size: 14px;
}
.empty {
    padding: 50px 20px;
    text-align: center;
    border: 1px dashed var(--border);
    border-radius: 15px;
    color: #777064;
}
.research-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 18px;
}
.research-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 15px;
    padding: 24px;
}
.research-card h3 {
    margin-bottom: 12px;
    font-size: 22px;
}
.research-card p {
    color: #625d54;
    line-height: 1.65;
}
.research-card a {
    display: inline-block;
    color: var(--green);
    margin-top: 18px;
    font-weight: bold;
}
.news-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 18px;
    padding: 30px;
    max-width: 800px;
}
.news-card h3 {
    font-size: 30px;
    margin-bottom: 15px;
}
.news-card p {
    color: #625d54;
    line-height: 1.7;
}
.news-card a {
    display: inline-block;
    margin-top: 20px;
    background: var(--green);
    color: white;
    text-decoration: none;
    padding: 12px 16px;
    border-radius: 8px;
}
footer {
    text-align: center;
    padding: 35px 20px;
    border-top: 1px solid var(--border);
    color: #777064;
    font-size: 13px;
}
/* EDITOR */
.modal {
    display: none;
    position: fixed;
    inset: 0;
    z-index: 500;
    background: rgba(0,0,0,.55);
    padding: 20px;
    overflow-y: auto;
}
.modal.show {
    display: flex;
    align-items: center;
    justify-content: center;
}
.modal-box {
    background: var(--background);
    width: min(850px, 100%);
    max-height: 92vh;
    overflow-y: auto;
    border-radius: 20px;
    padding: 25px;
    box-shadow: 0 20px 60px rgba(0,0,0,.25);
}
.modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 15px;
    margin-bottom: 25px;
}
.close {
    border: none;
    background: transparent;
    font-size: 28px;
    cursor: pointer;
}
.editor-section {
    background: var(--card);
    border: 1px solid var(--border);
    padding: 20px;
    border-radius: 14px;
    margin-bottom: 18px;
}
.editor-section h3 {
    margin-bottom: 15px;
}
label {
    display: block;
    font-size: 13px;
    font-weight: bold;
    margin: 14px 0 7px;
}
input,
textarea {
    width: 100%;
    border: 1px solid var(--border);
    background: white;
    border-radius: 8px;
    padding: 12px;
    font: inherit;
}
textarea {
    min-height: 110px;
    resize: vertical;
}
.editor-photo {
    display: grid;
    grid-template-columns: 80px 1fr auto;
    align-items: center;
    gap: 12px;
    padding: 10px 0;
    border-bottom: 1px solid var(--border);
}
.editor-photo img {
    width: 80px;
    height: 80px;
    object-fit: cover;
    border-radius: 8px;
}
.delete {
    border: none;
    background: #8a3030;
    color: white;
    border-radius: 7px;
    padding: 8px 10px;
    cursor: pointer;
}
.status {
    margin-top: 12px;
    padding: 12px;
    border-radius: 8px;
    background: #e8dfd0;
    display: none;
}
@media (max-width: 800px) {
    .hero {
        flex-direction: column;
        align-items: flex-start;
    }
    .hero-card {
        width: 100%;
        max-width: 350px;
    }
    .photo-grid {
        grid-template-columns: repeat(2, 1fr);
    }
    .research-grid {
        grid-template-columns: 1fr;
    }
    h1 {
        letter-spacing: -4px;
    }
}
@media (max-width: 520px) {
    .nav {
        align-items: flex-start;
        flex-direction: column;
    }
    nav {
        width: 100%;
    }
    nav button {
        flex: 1;
    }
    main {
        padding-top: 35px;
    }
    .photo-grid {
        grid-template-columns: 1fr;
    }
    .section-title {
        font-size: 38px;
    }
}
</style>
</head>
<body>
<header>
    <div class="nav">
        <div class="logo">Graysen</div>
        <nav>
            <button class="active" onclick="showPage('home', this)">Home</button>
            <button onclick="showPage('photography', this)">Photography</button>
            <button onclick="showPage('research', this)">Political Research</button>
            <button onclick="showPage('newspaper', this)">Newspaper</button>
        </nav>
    </div>
</header>
<main>
<!-- HOME -->
<section id="home" class="page active">
    <div class="hero">
        <div class="hero-text">
            <div class="eyebrow">Portfolio</div>
            <h1 id="homeName">Graysen</h1>
            <p id="homeBio">
                Welcome to my portfolio. This is where I share my photography,
                political research, newspaper work, and projects.
            </p>
            <button class="button" onclick="openEditor()">
                Edit Portfolio
            </button>
        </div>
        <div class="hero-card">
            <img id="profileImage" style="display:none;">
            <div id="profilePlaceholder" class="placeholder">
                Add a profile photo<br>
                from the editor.
            </div>
        </div>
    </div>
</section>
<!-- PHOTOGRAPHY -->
<section id="photography" class="page">
    <div class="eyebrow">Photography</div>
    <h2 class="section-title">Photography</h2>
    <p class="section-description" id="photoDescription">
        A collection of my photography and visual work.
    </p>
    <div id="photoGrid" class="photo-grid"></div>
</section>
<!-- RESEARCH -->
<section id="research" class="page">
    <div class="eyebrow">Research</div>
    <h2 class="section-title">Political Research</h2>
    <p class="section-description">
        Research, writing, and projects exploring politics and current issues.
    </p>
    <div id="researchGrid" class="research-grid"></div>
</section>
<!-- NEWSPAPER -->
<section id="newspaper" class="page">
    <div class="eyebrow">Journalism</div>
    <h2 class="section-title">Newspaper</h2>
    <div class="news-card">
        <h3 id="newsTitle">Newspaper</h3>
        <p id="newsDescription">
            Information about my newspaper work will appear here.
        </p>
        <a id="newsLink" href="#" target="_blank" style="display:none;">
            Visit Newspaper
        </a>
    </div>
</section>
</main>
<footer>
    © <span id="year"></span> Graysen
</footer>
<!-- PASSWORD MODAL -->
<div id="passwordModal" class="modal">
    <div class="modal-box" style="max-width:430px;">
        <div class="modal-header">
            <h2>Edit Portfolio</h2>
            <button class="close" onclick="closePassword()">×</button>
        </div>
        <p>Enter your editor code to continue.</p>
        <label>Editor Code</label>
        <input id="editorCode" type="password" inputmode="numeric">
        <button class="button" onclick="checkCode()">
            Continue
        </button>
        <div id="passwordError" class="status">
            Incorrect code.
        </div>
    </div>
</div>
<!-- EDITOR MODAL -->
<div id="editorModal" class="modal">
    <div class="modal-box">
        <div class="modal-header">
            <h2>Edit Portfolio</h2>
            <button class="close" onclick="closeEditor()">×</button>
        </div>
        <div class="editor-section">
            <h3>Home</h3>
            <label>Name</label>
            <input id="editName">
            <label>Bio</label>
            <textarea id="editBio"></textarea>
            <label>Profile Photo</label>
            <input id="profileUpload" type="file" accept="image/*">
        </div>
        <div class="editor-section">
            <h3>Photography</h3>
            <label>Photography Description</label>
            <textarea id="editPhotoDescription"></textarea>
            <label>Add Photos</label>
            <input id="photoUpload" type="file" accept="image/*" multiple>
            <p style="margin-top:10px;color:#777;">
                Maximum 25 photos. Photos are automatically compressed.
            </p>
            <div id="editorPhotos"></div>
        </div>
        <div class="editor-section">
            <h3>Political Research</h3>
            <div id="researchEditor"></div>
            <button class="button secondary" onclick="addResearch()">
                + Add Research
            </button>
        </div>
        <div class="editor-section">
            <h3>Newspaper</h3>
            <label>Newspaper Name</label>
            <input id="editNewsTitle">
            <label>Description</label>
            <textarea id="editNewsDescription"></textarea>
            <label>Website / Article Link</label>
            <input id="editNewsLink" type="url">
        </div>
        <button class="button" onclick="savePortfolio()">
            Save Changes
        </button>
        <div id="saveStatus" class="status">
            Changes saved on this device.
        </div>
    </div>
</div>
<script>
/* =========================
   PORTFOLIO DATA
========================= */
let portfolio = {
    name: "Graysen",
    bio: "Welcome to my portfolio. This is where I share my photography, political research, newspaper work, and projects.",
    profileImage: "",
    photoDescription: "A collection of my photography and visual work.",
    photos: [],
    research: [],
    newspaper: {
        title: "Newspaper",
        description: "Information about my newspaper work will appear here.",
        link: ""
    }
};
/* =========================
   LOAD SAVED DATA
========================= */
function loadPortfolio() {
    const saved = localStorage.getItem("graysenPortfolio");
    if (saved) {
        try {
            portfolio = JSON.parse(saved);
        } catch (error) {
            console.log("Could not load saved portfolio.");
        }
    }
    renderPortfolio();
}
/* =========================
   PAGE NAVIGATION
========================= */
function showPage(pageId, button) {
    document.querySelectorAll(".page").forEach(page => {
        page.classList.remove("active");
    });
    document.getElementById(pageId).classList.add("active");
    document.querySelectorAll("nav button").forEach(btn => {
        btn.classList.remove("active");
    });
    button.classList.add("active");
    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });
}
/* =========================
   RENDER WEBSITE
========================= */
function renderPortfolio() {
    document.getElementById("homeName").textContent =
        portfolio.name || "Graysen";
    document.getElementById("homeBio").textContent =
        portfolio.bio || "";
    document.getElementById("photoDescription").textContent =
        portfolio.photoDescription || "";
    const profile = document.getElementById("profileImage");
    const placeholder = document.getElementById("profilePlaceholder");
    if (portfolio.profileImage) {
        profile.src = portfolio.profileImage;
        profile.style.display = "block";
        placeholder.style.display = "none";
    } else {
        profile.style.display = "none";
        placeholder.style.display = "block";
    }
    /* PHOTOS */
    const grid = document.getElementById("photoGrid");
    grid.innerHTML = "";
    if (!portfolio.photos.length) {
        grid.innerHTML = `
            <div class="empty">
                No photography has been added yet.
            </div>
        `;
    } else {
        portfolio.photos.forEach((photo, index) => {
            const item = document.createElement("div");
            item.className = "photo-item";
            item.innerHTML = `
                <img src="${photo.image}" alt="${escapeHTML(photo.caption || "Photography")}">
                <div class="photo-caption">
                    ${escapeHTML(photo.caption || "Photography")}
                </div>
            `;
            item.querySelector("img").onclick = () => {
                window.open(photo.image, "_blank");
            };
            grid.appendChild(item);
        });
    }
    /* RESEARCH */
    const researchGrid = document.getElementById("researchGrid");
    researchGrid.innerHTML = "";
    if (!portfolio.research.length) {
        researchGrid.innerHTML = `
            <div class="empty">
                No research projects have been added yet.
            </div>
        `;
    } else {
        portfolio.research.forEach(item => {
            const card = document.createElement("div");
            card.className = "research-card";
            card.innerHTML = `
                <h3>${escapeHTML(item.title)}</h3>
                <p>${escapeHTML(item.description)}</p>
                ${
                    item.link
                    ? `<a href="${escapeAttribute(item.link)}" target="_blank">Read More →</a>`
                    : ""
                }
            `;
            researchGrid.appendChild(card);
        });
    }
    /* NEWSPAPER */
    document.getElementById("newsTitle").textContent =
        portfolio.newspaper.title || "Newspaper";
    document.getElementById("newsDescription").textContent =
        portfolio.newspaper.description || "";
    const newsLink = document.getElementById("newsLink");
    if (portfolio.newspaper.link) {
        newsLink.href = portfolio.newspaper.link;
        newsLink.style.display = "inline-block";
    } else {
        newsLink.style.display = "none";
    }
}
/* =========================
   EDITOR
========================= */
function openEditor() {
    document.getElementById("passwordModal").classList.add("show");
    setTimeout(() => {
        document.getElementById("editorCode").focus();
    }, 100);
}
function closePassword() {
    document.getElementById("passwordModal").classList.remove("show");
    document.getElementById("editorCode").value = "";
    document.getElementById("passwordError").style.display = "none";
}
function checkCode() {
    const code = document.getElementById("editorCode").value;
    if (code === "4547") {
        closePassword();
        openEditorPanel();
    } else {
        document.getElementById("passwordError").style.display = "block";
    }
}
function openEditorPanel() {
    document.getElementById("editorModal").classList.add("show");
    document.getElementById("editName").value =
        portfolio.name;
    document.getElementById("editBio").value =
        portfolio.bio;
    document.getElementById("editPhotoDescription").value =
        portfolio.photoDescription;
    document.getElementById("editNewsTitle").value =
        portfolio.newspaper.title;
    document.getElementById("editNewsDescription").value =
        portfolio.newspaper.description;
    document.getElementById("editNewsLink").value =
        portfolio.newspaper.link;
    renderEditorPhotos();
    renderResearchEditor();
}
function closeEditor() {
    document.getElementById("editorModal").classList.remove("show");
}
/* =========================
   PHOTO COMPRESSION
========================= */
function compressImage(file, maxWidth = 1200, quality = 0.72) {
    return new Promise((resolve, reject) => {
        const reader = new FileReader();
        reader.onload = event => {
            const img = new Image();
            img.onload = () => {
                let width = img.width;
                let height = img.height;
                if (width > maxWidth) {
                    height = height * (maxWidth / width);
                    width = maxWidth;
                }
                const canvas = document.createElement("canvas");
                canvas.width = width;
                canvas.height = height;
                const ctx = canvas.getContext("2d");
                ctx.drawImage(
                    img,
                    0,
                    0,
                    width,
                    height
                );
                resolve(
                    canvas.toDataURL(
                        "image/jpeg",
                        quality
                    )
                );
            };
            img.onerror = reject;
            img.src = event.target.result;
        };
        reader.onerror = reject;
        reader.readAsDataURL(file);
    });
}
/* =========================
   PROFILE PHOTO
========================= */
document.getElementById("profileUpload")
.addEventListener("change", async function() {
    const file = this.files[0];
    if (!file) return;
    try {
        const compressed = await compressImage(
            file,
            1000,
            0.72
        );
        portfolio.profileImage = compressed;
        renderPortfolio();
    } catch (error) {
        alert("Could not process that image.");
    }
});
/* =========================
   ADD PHOTOS
========================= */
document.getElementById("photoUpload")
.addEventListener("change", async function() {
    const files = Array.from(this.files);
    if (!files.length) return;
    if (portfolio.photos.length >= 25) {
        alert("You already have 25 photos.");
        this.value = "";
        return;
    }
    const remaining = 25 - portfolio.photos.length;
    const filesToAdd = files.slice(0, remaining);
    for (const file of filesToAdd) {
        try {
            const compressed = await compressImage(
                file,
                1200,
                0.65
            );
            portfolio.photos.push({
                image: compressed,
                caption: file.name
                    .replace(/\.[^/.]+$/, "")
            });
        } catch (error) {
            console.log(
                "Could not process image:",
                file.name
            );
        }
    }
    renderEditorPhotos();
    renderPortfolio();
    this.value = "";
});
/* =========================
   EDITOR PHOTOS
========================= */
function renderEditorPhotos() {
    const container =
        document.getElementById("editorPhotos");
    container.innerHTML = "";
    portfolio.photos.forEach((photo, index) => {
        const row =
            document.createElement("div");
        row.className = "editor-photo";
        row.innerHTML = `
            <img src="${photo.image}">
            <input
                value="${escapeAttribute(photo.caption || "")}"
                placeholder="Caption"
            >
            <button class="delete">
                Delete
            </button>
        `;
        row.querySelector("input")
        .addEventListener("input", event => {
            portfolio.photos[index].caption =
                event.target.value;
        });
        row.querySelector(".delete")
        .onclick = () => {
            portfolio.photos.splice(index, 1);
            renderEditorPhotos();
            renderPortfolio();
        };
        container.appendChild(row);
    });
}
/* =========================
   RESEARCH EDITOR
========================= */
function renderResearchEditor() {
    const container =
        document.getElementById("researchEditor");
    container.innerHTML = "";
    portfolio.research.forEach((item, index) => {
        const section =
            document.createElement("div");
        section.style.marginBottom = "20px";
        section.style.paddingBottom = "20px";
        section.style.borderBottom =
            "1px solid var(--border)";
        section.innerHTML = `
            <label>Title</label>
            <input
                class="research-title"
                value="${escapeAttribute(item.title || "")}"
            >
            <label>Description</label>
            <textarea
                class="research-description"
            >${escapeHTML(item.description || "")}</textarea>
            <label>Link</label>
            <input
                class="research-link"
                value="${escapeAttribute(item.link || "")}"
                placeholder="https://..."
            >
            <button class="delete">
                Delete Research
            </button>
        `;
        section.querySelector(".research-title")
        .addEventListener("input", event => {
            portfolio.research[index].title =
                event.target.value;
        });
        section.querySelector(".research-description")
        .addEventListener("input", event => {
            portfolio.research[index].description =
                event.target.value;
        });
        section.querySelector(".research-link")
        .addEventListener("input", event => {
            portfolio.research[index].link =
                event.target.value;
        });
        section.querySelector(".delete")
        .onclick = () => {
            portfolio.research.splice(index, 1);
            renderResearchEditor();
        };
        container.appendChild(section);
    });
}
function addResearch() {
    portfolio.research.push({
        title: "New Research",
        description: "Describe your research here.",
        link: ""
    });
    renderResearchEditor();
}
/* =========================
   SAVE
========================= */
function savePortfolio() {
    portfolio.name =
        document.getElementById("editName").value;
    portfolio.bio =
        document.getElementById("editBio").value;
    portfolio.photoDescription =
        document.getElementById("editPhotoDescription").value;
    portfolio.newspaper.title =
        document.getElementById("editNewsTitle").value;
    portfolio.newspaper.description =
        document.getElementById("editNewsDescription").value;
    portfolio.newspaper.link =
        document.getElementById("editNewsLink").value;
    localStorage.setItem(
        "graysenPortfolio",
        JSON.stringify(portfolio)
    );
    renderPortfolio();
    const status =
        document.getElementById("saveStatus");
    status.textContent =
        "Changes saved on this device.";
    status.style.display = "block";
    setTimeout(() => {
        status.style.display = "none";
    }, 3500);
}
/* =========================
   SECURITY / HTML HELPERS
========================= */
function escapeHTML(value) {
    return String(value)
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;")
        .replace(/"/g, "&quot;")
        .replace(/'/g, "&#039;");
}
function escapeAttribute(value) {
    return escapeHTML(value);
}
/* =========================
   START
========================= */
document.getElementById("year").textContent =
    new Date().getFullYear();
loadPortfolio();
</script>
</body>
</html>