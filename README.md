<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Graysen — Portfolio</title>
<style>
:root {
    --cream: #f5efe4;
    --cream-2: #eee5d5;
    --paper: #fffaf2;
    --black: #171714;
    --muted: #706b61;
    --green: #315d48;
    --green-dark: #234535;
    --line: #d8cdbb;
    --shadow: 0 20px 60px rgba(35, 31, 24, .10);
}
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}
html {
    scroll-behavior: smooth;
}
body {
    background: var(--cream);
    color: var(--black);
    font-family:
        Inter,
        -apple-system,
        BlinkMacSystemFont,
        "Segoe UI",
        Arial,
        sans-serif;
    line-height: 1.5;
}
/* ---------- NAVIGATION ---------- */
header {
    position: sticky;
    top: 0;
    z-index: 100;
    background: rgba(245,239,228,.88);
    backdrop-filter: blur(18px);
    border-bottom: 1px solid rgba(216,205,187,.7);
}
.navbar {
    max-width: 1180px;
    margin: auto;
    padding: 18px 24px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 25px;
}
.logo {
    font-family: Georgia, serif;
    font-size: 30px;
    font-weight: 700;
    letter-spacing: -1.5px;
}
.nav-links {
    display: flex;
    gap: 5px;
    flex-wrap: wrap;
}
.nav-links button {
    border: 0;
    background: transparent;
    color: var(--black);
    padding: 9px 13px;
    border-radius: 8px;
    cursor: pointer;
    font-size: 14px;
    transition: .2s ease;
}
.nav-links button:hover,
.nav-links button.active {
    background: var(--green);
    color: white;
}
/* ---------- GENERAL ---------- */
.container {
    max-width: 1180px;
    margin: auto;
    padding: 0 24px;
}
.page {
    display: none;
    animation: pageIn .35s ease;
}
.page.active {
    display: block;
}
@keyframes pageIn {
    from {
        opacity: 0;
        transform: translateY(12px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}
.eyebrow {
    color: var(--green);
    font-size: 11px;
    font-weight: 800;
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 18px;
}
.section {
    padding: 90px 0;
}
.section-heading {
    max-width: 760px;
    margin-bottom: 42px;
}
.section-heading h2 {
    font-family: Georgia, serif;
    font-size: clamp(42px, 6vw, 72px);
    letter-spacing: -3px;
    line-height: .98;
    margin-bottom: 18px;
}
.section-heading p {
    color: var(--muted);
    font-size: 17px;
    max-width: 680px;
}
/* ---------- HOME ---------- */
.hero {
    min-height: calc(100vh - 76px);
    display: grid;
    grid-template-columns: 1.35fr .65fr;
    align-items: center;
    gap: 80px;
    padding: 70px 0;
}
.hero h1 {
    font-family: Georgia, serif;
    font-size: clamp(70px, 12vw, 150px);
    line-height: .82;
    letter-spacing: -8px;
    margin-bottom: 35px;
}
.hero-description {
    color: var(--muted);
    font-size: 19px;
    line-height: 1.75;
    max-width: 650px;
}
.profile-frame {
    position: relative;
    aspect-ratio: 4 / 5;
    max-width: 390px;
    margin-left: auto;
    border-radius: 28px;
    overflow: hidden;
    background: var(--cream-2);
    border: 1px solid var(--line);
    box-shadow: var(--shadow);
}
.profile-frame img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}
.profile-placeholder {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    padding: 35px;
    color: var(--muted);
}
.primary-button {
    margin-top: 30px;
    border: 0;
    border-radius: 10px;
    background: var(--green);
    color: white;
    padding: 14px 20px;
    font-size: 14px;
    font-weight: 700;
    cursor: pointer;
    transition: .2s ease;
}
.primary-button:hover {
    background: var(--green-dark);
    transform: translateY(-2px);
}
/* ---------- PHOTOGRAPHY ---------- */
.photo-grid {
    columns: 3 260px;
    column-gap: 18px;
}
.photo-card {
    break-inside: avoid;
    margin-bottom: 18px;
    background: var(--paper);
    border: 1px solid var(--line);
    border-radius: 16px;
    overflow: hidden;
    box-shadow: 0 8px 25px rgba(35,31,24,.05);
}
.photo-card img {
    width: 100%;
    display: block;
    cursor: zoom-in;
}
.photo-caption {
    padding: 13px 15px;
    font-size: 13px;
    color: var(--muted);
}
/* ---------- RESEARCH ---------- */
.research-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
}
.research-card {
    background: var(--paper);
    border: 1px solid var(--line);
    border-radius: 18px;
    padding: 27px;
    transition: .25s ease;
}
.research-card:hover {
    transform: translateY(-4px);
    box-shadow: var(--shadow);
}
.research-number {
    color: var(--green);
    font-size: 12px;
    font-weight: 800;
    margin-bottom: 18px;
}
.research-card h3 {
    font-family: Georgia, serif;
    font-size: 27px;
    line-height: 1.1;
    margin-bottom: 14px;
}
.research-card p {
    color: var(--muted);
    line-height: 1.7;
}
.research-card a {
    display: inline-block;
    margin-top: 20px;
    color: var(--green);
    text-decoration: none;
    font-weight: 700;
}
/* ---------- NEWSPAPER ---------- */
.newspaper-card {
    background: var(--black);
    color: white;
    border-radius: 24px;
    padding: clamp(30px, 6vw, 65px);
    max-width: 900px;
}
.newspaper-card .eyebrow {
    color: #a9c9b6;
}
.newspaper-card h2 {
    font-family: Georgia, serif;
    font-size: clamp(40px, 7vw, 75px);
    line-height: .95;
    letter-spacing: -3px;
    margin-bottom: 20px;
}
.newspaper-card p {
    color: #c8c4bc;
    max-width: 650px;
    line-height: 1.75;
}
.newspaper-link {
    display: inline-block;
    margin-top: 27px;
    background: white;
    color: var(--black);
    text-decoration: none;
    padding: 13px 18px;
    border-radius: 9px;
    font-weight: 700;
}
/* ---------- EMPTY ---------- */
.empty {
    background: rgba(255,250,242,.45);
    border: 1px dashed var(--line);
    border-radius: 16px;
    padding: 50px 20px;
    text-align: center;
    color: var(--muted);
}
/* ---------- FOOTER ---------- */
footer {
    border-top: 1px solid var(--line);
    padding: 35px 24px;
    text-align: center;
    color: var(--muted);
    font-size: 13px;
}
/* ---------- MODALS ---------- */
.modal {
    display: none;
    position: fixed;
    inset: 0;
    z-index: 500;
    padding: 18px;
    background: rgba(20,18,14,.65);
    backdrop-filter: blur(8px);
    overflow-y: auto;
}
.modal.open {
    display: flex;
    align-items: center;
    justify-content: center;
}
.modal-box {
    width: min(900px, 100%);
    max-height: 94vh;
    overflow-y: auto;
    background: var(--cream);
    border-radius: 22px;
    padding: 27px;
    box-shadow: 0 30px 100px rgba(0,0,0,.3);
}
.modal-small {
    width: min(430px, 100%);
}
.modal-top {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 25px;
}
.modal-top h2 {
    font-family: Georgia, serif;
    font-size: 30px;
}
.close {
    border: 0;
    background: transparent;
    font-size: 30px;
    cursor: pointer;
    color: var(--black);
}
.editor-section {
    background: var(--paper);
    border: 1px solid var(--line);
    border-radius: 15px;
    padding: 21px;
    margin-bottom: 17px;
}
.editor-section h3 {
    font-family: Georgia, serif;
    font-size: 22px;
    margin-bottom: 16px;
}
label {
    display: block;
    margin: 14px 0 7px;
    font-size: 12px;
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: 1px;
}
input,
textarea {
    width: 100%;
    border: 1px solid var(--line);
    border-radius: 9px;
    background: white;
    padding: 12px;
    font: inherit;
    color: var(--black);
    outline: none;
}
input:focus,
textarea:focus {
    border-color: var(--green);
}
textarea {
    min-height: 115px;
    resize: vertical;
}
.editor-photo {
    display: grid;
    grid-template-columns: 70px 1fr auto;
    gap: 12px;
    align-items: center;
    padding: 12px 0;
    border-bottom: 1px solid var(--line);
}
.editor-photo img {
    width: 70px;
    height: 70px;
    object-fit: cover;
    border-radius: 8px;
}
.delete-button {
    border: 0;
    background: #8c3535;
    color: white;
    padding: 8px 10px;
    border-radius: 7px;
    cursor: pointer;
}
.add-button {
    border: 1px solid var(--line);
    background: transparent;
    color: var(--black);
    padding: 10px 14px;
    border-radius: 8px;
    cursor: pointer;
    font-weight: 700;
    margin-top: 15px;
}
.status {
    display: none;
    padding: 12px;
    border-radius: 9px;
    background: #e3ddcf;
    color: var(--black);
    margin-top: 15px;
}
/* ---------- MOBILE ---------- */
@media(max-width: 800px) {
    .navbar {
        flex-direction: column;
        align-items: flex-start;
    }
    .nav-links {
        width: 100%;
        overflow-x: auto;
        flex-wrap: nowrap;
        padding-bottom: 3px;
    }
    .nav-links button {
        white-space: nowrap;
    }
    .hero {
        grid-template-columns: 1fr;
        gap: 45px;
        padding-top: 50px;
    }
    .hero h1 {
        letter-spacing: -5px;
    }
    .profile-frame {
        width: min(100%, 390px);
        margin: 0;
    }
    .research-grid {
        grid-template-columns: 1fr;
    }
    .section {
        padding: 65px 0;
    }
}
@media(max-width: 500px) {
    .container {
        padding: 0 17px;
    }
    .navbar {
        padding: 15px 17px;
    }
    .logo {
        font-size: 26px;
    }
    .hero h1 {
        font-size: 70px;
    }
    .editor-photo {
        grid-template-columns: 55px 1fr;
    }
    .editor-photo img {
        width: 55px;
        height: 55px;
    }
    .editor-photo .delete-button {
        grid-column: 2;
        width: fit-content;
    }
}
</style>
</head>
<body>
<header>
    <div class="navbar">
        <div class="logo">Graysen</div>
        <div class="nav-links">
            <button class="active"
                onclick="showPage('home', this)">
                Home
            </button>
            <button
                onclick="showPage('photography', this)">
                Photography
            </button>
            <button
                onclick="showPage('research', this)">
                Political Research
            </button>
            <button
                onclick="showPage('newspaper', this)">
                Newspaper
            </button>
        </div>
    </div>
</header>
<main class="container">
<!-- ================= HOME ================= -->
<section id="home" class="page active">
    <div class="hero">
        <div>
            <div class="eyebrow">
                Portfolio
            </div>
            <h1 id="nameText">
                Graysen
            </h1>
            <p id="bioText" class="hero-description">
                Welcome to my portfolio. Here you'll find my photography,
                political research, newspaper work, and creative projects.
            </p>
            <button class="primary-button"
                onclick="openPassword()">
                Edit Portfolio
            </button>
        </div>
        <div class="profile-frame">
            <img
                id="profileImage"
                style="display:none;"
                alt="Graysen">
            <div
                id="profilePlaceholder"
                class="profile-placeholder">
                Your profile photo can go here.
            </div>
        </div>
    </div>
</section>
<!-- ================= PHOTOGRAPHY ================= -->
<section id="photography" class="page">
    <div class="section">
        <div class="section-heading">
            <div class="eyebrow">
                Visual Work
            </div>
            <h2>
                Photography
            </h2>
            <p id="photoDescription">
                A collection of my photography and visual work.
            </p>
        </div>
        <div id="photoGrid" class="photo-grid"></div>
    </div>
</section>
<!-- ================= RESEARCH ================= -->
<section id="research" class="page">
    <div class="section">
        <div class="section-heading">
            <div class="eyebrow">
                Research & Writing
            </div>
            <h2>
                Political Research
            </h2>
            <p>
                Research projects, writing, and analysis exploring politics,
                government, public policy, and current issues.
            </p>
        </div>
        <div id="researchGrid" class="research-grid"></div>
    </div>
</section>
<!-- ================= NEWSPAPER ================= -->
<section id="newspaper" class="page">
    <div class="section">
        <div class="newspaper-card">
            <div class="eyebrow">
                Journalism
            </div>
            <h2 id="newspaperTitle">
                Newspaper
            </h2>
            <p id="newspaperDescription">
                Information about my newspaper work will appear here.
            </p>
            <a
                id="newspaperLink"
                class="newspaper-link"
                target="_blank"
                style="display:none;">
                Visit Newspaper →
            </a>
        </div>
    </div>
</section>
</main>
<footer>
    © <span id="year"></span> Graysen
</footer>
<!-- ================= PASSWORD ================= -->
<div id="passwordModal" class="modal">
    <div class="modal-box modal-small">
        <div class="modal-top">
            <h2>Edit Portfolio</h2>
            <button class="close"
                onclick="closePassword()">
                ×
            </button>
        </div>
        <p>
            Enter your editor code to access your portfolio editor.
        </p>
        <label>
            Editor Code
        </label>
        <input
            id="passwordInput"
            type="password"
            inputmode="numeric"
            autocomplete="off">
        <button class="primary-button"
            onclick="checkPassword()">
            Continue
        </button>
        <div id="passwordError"
            class="status">
            Incorrect code.
        </div>
    </div>
</div>
<!-- ================= EDITOR ================= -->
<div id="editorModal" class="modal">
    <div class="modal-box">
        <div class="modal-top">
            <h2>
                Edit Portfolio
            </h2>
            <button class="close"
                onclick="closeEditor()">
                ×
            </button>
        </div>
        <!-- HOME EDITOR -->
        <div class="editor-section">
            <h3>
                Home
            </h3>
            <label>
                Name
            </label>
            <input id="editName">
            <label>
                Bio
            </label>
            <textarea id="editBio"></textarea>
            <label>
                Profile Photo
            </label>
            <input
                id="profileUpload"
                type="file"
                accept="image/*">
        </div>
        <!-- PHOTO EDITOR -->
        <div class="editor-section">
            <h3>
                Photography
            </h3>
            <label>
                Description
            </label>
            <textarea
                id="editPhotoDescription"></textarea>
            <label>
                Add Photos
            </label>
            <input
                id="photoUpload"
                type="file"
                accept="image/*"
                multiple>
            <p style="margin-top:10px;color:var(--muted);font-size:13px;">
                Up to 25 photos. Images are automatically compressed.
            </p>
            <div id="editorPhotos"></div>
        </div>
        <!-- RESEARCH EDITOR -->
        <div class="editor-section">
            <h3>
                Political Research
            </h3>
            <div id="researchEditor"></div>
            <button
                class="add-button"
                onclick="addResearch()">
                + Add Research
            </button>
        </div>
        <!-- NEWSPAPER EDITOR -->
        <div class="editor-section">
            <h3>
                Newspaper
            </h3>
            <label>
                Newspaper Name
            </label>
            <input id="editNewspaperTitle">
            <label>
                Description
            </label>
            <textarea
                id="editNewspaperDescription"></textarea>
            <label>
                Website / Article Link
            </label>
            <input
                id="editNewspaperLink"
                type="url"
                placeholder="https://...">
        </div>
        <button
            class="primary-button"
            onclick="savePortfolio()">
            Save Changes
        </button>
        <div
            id="saveStatus"
            class="status">
            Changes saved on this device.
        </div>
    </div>
</div>
<script>
/* =====================================================
   PORTFOLIO DATA
===================================================== */
let portfolio = {
    name: "Graysen",
    bio:
        "Welcome to my portfolio. Here you'll find my photography, political research, newspaper work, and creative projects.",
    profileImage: "",
    photoDescription:
        "A collection of my photography and visual work.",
    photos: [],
    research: [],
    newspaper: {
        title: "Newspaper",
        description:
            "Information about my newspaper work will appear here.",
        link: ""
    }
};
/* =====================================================
   LOAD
===================================================== */
function loadPortfolio() {
    const saved =
        localStorage.getItem("graysenPortfolio");
    if (saved) {
        try {
            const parsed =
                JSON.parse(saved);
            portfolio = {
                ...portfolio,
                ...parsed,
                newspaper: {
                    ...portfolio.newspaper,
                    ...(parsed.newspaper || {})
                }
            };
        } catch {
            console.log(
                "Saved portfolio could not be loaded."
            );
        }
    }
    renderPortfolio();
}
/* =====================================================
   PAGE SWITCHING
===================================================== */
function showPage(page, button) {
    document
        .querySelectorAll(".page")
        .forEach(element => {
            element.classList.remove("active");
        });
    document
        .getElementById(page)
        .classList.add("active");
    document
        .querySelectorAll(".nav-links button")
        .forEach(element => {
            element.classList.remove("active");
        });
    button.classList.add("active");
    window.scrollTo({
        top: 0,
        behavior: "smooth"
    });
}
/* =====================================================
   RENDER
===================================================== */
function renderPortfolio() {
    document.getElementById("nameText")
        .textContent =
        portfolio.name || "Graysen";
    document.getElementById("bioText")
        .textContent =
        portfolio.bio || "";
    document.getElementById("photoDescription")
        .textContent =
        portfolio.photoDescription || "";
    /* PROFILE */
    const profile =
        document.getElementById("profileImage");
    const placeholder =
        document.getElementById("profilePlaceholder");
    if (portfolio.profileImage) {
        profile.src =
            portfolio.profileImage;
        profile.style.display =
            "block";
        placeholder.style.display =
            "none";
    } else {
        profile.style.display =
            "none";
        placeholder.style.display =
            "flex";
    }
    /* PHOTOS */
    const grid =
        document.getElementById("photoGrid");
    grid.innerHTML = "";
    if (!portfolio.photos.length) {
        grid.innerHTML = `
            <div class="empty">
                No photographs have been added yet.
            </div>
        `;
    } else {
        portfolio.photos.forEach(photo => {
            const card =
                document.createElement("div");
            card.className =
                "photo-card";
            const image =
                document.createElement("img");
            image.src =
                photo.image;
            image.alt =
                photo.caption || "Photography";
            image.onclick = () => {
                window.open(
                    photo.image,
                    "_blank"
                );
            };
            const caption =
                document.createElement("div");
            caption.className =
                "photo-caption";
            caption.textContent =
                photo.caption || "Photography";
            card.appendChild(image);
            card.appendChild(caption);
            grid.appendChild(card);
        });
    }
    /* RESEARCH */
    const researchGrid =
        document.getElementById(
            "researchGrid"
        );
    researchGrid.innerHTML = "";
    if (!portfolio.research.length) {
        researchGrid.innerHTML = `
            <div class="empty">
                No research projects have been added yet.
            </div>
        `;
    } else {
        portfolio.research.forEach(
            (item, index) => {
                const card =
                    document.createElement("article");
                card.className =
                    "research-card";
                card.innerHTML = `
                    <div class="research-number">
                        ${String(index + 1).padStart(2, "0")}
                    </div>
                    <h3>
                        ${safe(item.title)}
                    </h3>
                    <p>
                        ${safe(item.description)}
                    </p>
                    ${
                        item.link
                        ? `
                            <a
                                href="${safeAttribute(item.link)}"
                                target="_blank"
                                rel="noopener">
                                Read More →
                            </a>
                        `
                        : ""
                    }
                `;
                researchGrid.appendChild(card);
            }
        );
    }
    /* NEWSPAPER */
    document.getElementById(
        "newspaperTitle"
    ).textContent =
        portfolio.newspaper.title ||
        "Newspaper";
    document.getElementById(
        "newspaperDescription"
    ).textContent =
        portfolio.newspaper.description ||
        "";
    const newspaperLink =
        document.getElementById(
            "newspaperLink"
        );
    if (portfolio.newspaper.link) {
        newspaperLink.href =
            portfolio.newspaper.link;
        newspaperLink.style.display =
            "inline-block";
    } else {
        newspaperLink.style.display =
            "none";
    }
}
/* =====================================================
   PASSWORD
===================================================== */
function openPassword() {
    document
        .getElementById("passwordModal")
        .classList.add("open");
    setTimeout(() => {
        document
            .getElementById("passwordInput")
            .focus();
    }, 100);
}
function closePassword() {
    document
        .getElementById("passwordModal")
        .classList.remove("open");
    document
        .getElementById("passwordInput")
        .value = "";
    document
        .getElementById("passwordError")
        .style.display = "none";
}
function checkPassword() {
    const code =
        document.getElementById(
            "passwordInput"
        ).value;
    if (code === "4547") {
        closePassword();
        openEditor();
    } else {
        document
            .getElementById("passwordError")
            .style.display = "block";
    }
}
/* =====================================================
   EDITOR
===================================================== */
function openEditor() {
    document
        .getElementById("editorModal")
        .classList.add("open");
    document.getElementById("editName")
        .value =
        portfolio.name;
    document.getElementById("editBio")
        .value =
        portfolio.bio;
    document.getElementById(
        "editPhotoDescription"
    ).value =
        portfolio.photoDescription;
    document.getElementById(
        "editNewspaperTitle"
    ).value =
        portfolio.newspaper.title;
    document.getElementById(
        "editNewspaperDescription"
    ).value =
        portfolio.newspaper.description;
    document.getElementById(
        "editNewspaperLink"
    ).value =
        portfolio.newspaper.link;
    renderEditorPhotos();
    renderResearchEditor();
}
function closeEditor() {
    document
        .getElementById("editorModal")
        .classList.remove("open");
}
/* =====================================================
   IMAGE COMPRESSION
===================================================== */
function compressImage(
    file,
    maxWidth = 1200,
    quality = .68
) {
    return new Promise(
        (resolve, reject) => {
            const reader =
                new FileReader();
            reader.onload = event => {
                const image =
                    new Image();
                image.onload = () => {
                    let width =
                        image.width;
                    let height =
                        image.height;
                    if (width > maxWidth) {
                        height =
                            height *
                            (maxWidth / width);
                        width =
                            maxWidth;
                    }
                    const canvas =
                        document.createElement(
                            "canvas"
                        );
                    canvas.width =
                        width;
                    canvas.height =
                        height;
                    const context =
                        canvas.getContext(
                            "2d"
                        );
                    context.drawImage(
                        image,
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
                image.onerror =
                    reject;
                image.src =
                    event.target.result;
            };
            reader.onerror =
                reject;
            reader.readAsDataURL(file);
        }
    );
}
/* =====================================================
   PROFILE UPLOAD
===================================================== */
document
    .getElementById("profileUpload")
    .addEventListener(
        "change",
        async function() {
            const file =
                this.files[0];
            if (!file) return;
            try {
                portfolio.profileImage =
                    await compressImage(
                        file,
                        1000,
                        .70
                    );
                renderPortfolio();
            } catch {
                alert(
                    "The profile photo could not be processed."
                );
            }
        }
    );
/* =====================================================
   PHOTO UPLOAD
===================================================== */
document
    .getElementById("photoUpload")
    .addEventListener(
        "change",
        async function() {
            const files =
                Array.from(this.files);
            if (!files.length) return;
            const remaining =
                25 -
                portfolio.photos.length;
            if (remaining <= 0) {
                alert(
                    "You already have 25 photos."
                );
                this.value = "";
                return;
            }
            for (
                const file of
                files.slice(0, remaining)
            ) {
                try {
                    const image =
                        await compressImage(
                            file,
                            1200,
                            .65
                        );
                    portfolio.photos.push({
                        image: image,
                        caption:
                            file.name
                                .replace(
                                    /\.[^/.]+$/,
                                    ""
                                )
                    });
                } catch {
                    console.log(
                        "Could not process:",
                        file.name
                    );
                }
            }
            renderEditorPhotos();
            renderPortfolio();
            this.value = "";
        }
    );
/* =====================================================
   EDITOR PHOTO LIST
===================================================== */
function renderEditorPhotos() {
    const container =
        document.getElementById(
            "editorPhotos"
        );
    container.innerHTML = "";
    portfolio.photos.forEach(
        (photo, index) => {
            const row =
                document.createElement("div");
            row.className =
                "editor-photo";
            const image =
                document.createElement("img");
            image.src =
                photo.image;
            const input =
                document.createElement("input");
            input.value =
                photo.caption || "";
            input.placeholder =
                "Photo caption";
            input.addEventListener(
                "input",
                event => {
                    portfolio.photos[index]
                        .caption =
                        event.target.value;
                }
            );
            const deleteButton =
                document.createElement(
                    "button"
                );
            deleteButton.className =
                "delete-button";
            deleteButton.textContent =
                "Delete";
            deleteButton.onclick =
                () => {
                    portfolio.photos
                        .splice(index, 1);
                    renderEditorPhotos();
                    renderPortfolio();
                };
            row.appendChild(image);
            row.appendChild(input);
            row.appendChild(deleteButton);
            container.appendChild(row);
        }
    );
}
/* =====================================================
   RESEARCH EDITOR
===================================================== */
function renderResearchEditor() {
    const container =
        document.getElementById(
            "researchEditor"
        );
    container.innerHTML = "";
    portfolio.research.forEach(
        (item, index) => {
            const wrapper =
                document.createElement("div");
            wrapper.style.marginBottom =
                "22px";
            wrapper.style.paddingBottom =
                "22px";
            wrapper.style.borderBottom =
                "1px solid var(--line)";
            wrapper.innerHTML = `
                <label>Title</label>
                <input
                    class="research-title"
                    value="${safeAttribute(item.title)}"
                >
                <label>Description</label>
                <textarea
                    class="research-description"
                >${safe(item.description)}</textarea>
                <label>Link</label>
                <input
                    class="research-link"
                    type="url"
                    placeholder="https://..."
                    value="${safeAttribute(item.link)}"
                >
                <button
                    class="delete-button"
                    style="margin-top:12px;">
                    Delete Research
                </button>
            `;
            wrapper
                .querySelector(
                    ".research-title"
                )
                .addEventListener(
                    "input",
                    event => {
                        portfolio
                            .research[index]
                            .title =
                            event.target.value;
                    }
                );
            wrapper
                .querySelector(
                    ".research-description"
                )
                .addEventListener(
                    "input",
                    event => {
                        portfolio
                            .research[index]
                            .description =
                            event.target.value;
                    }
                );
            wrapper
                .querySelector(
                    ".research-link"
                )
                .addEventListener(
                    "input",
                    event => {
                        portfolio
                            .research[index]
                            .link =
                            event.target.value;
                    }
                );
            wrapper
                .querySelector(
                    ".delete-button"
                )
                .onclick =
                () => {
                    portfolio
                        .research
                        .splice(index, 1);
                    renderResearchEditor();
                };
            container.appendChild(wrapper);
        }
    );
}
/* =====================================================
   ADD RESEARCH
===================================================== */
function addResearch() {
    portfolio.research.push({
        title: "New Research",
        description:
            "Describe this research project here.",
        link: ""
    });
    renderResearchEditor();
}
/* =====================================================
   SAVE
===================================================== */
function savePortfolio() {
    portfolio.name =
        document.getElementById(
            "editName"
        ).value;
    portfolio.bio =
        document.getElementById(
            "editBio"
        ).value;
    portfolio.photoDescription =
        document.getElementById(
            "editPhotoDescription"
        ).value;
    portfolio.newspaper = {
        title:
            document.getElementById(
                "editNewspaperTitle"
            ).value,
        description:
            document.getElementById(
                "editNewspaperDescription"
            ).value,
        link:
            document.getElementById(
                "editNewspaperLink"
            ).value
    };
    localStorage.setItem(
        "graysenPortfolio",
        JSON.stringify(portfolio)
    );
    renderPortfolio();
    const status =
        document.getElementById(
            "saveStatus"
        );
    status.textContent =
        "Saved successfully on this device.";
    status.style.display =
        "block";
    setTimeout(() => {
        status.style.display =
            "none";
    }, 3500);
}
/* =====================================================
   SAFE TEXT
===================================================== */
function safe(value) {
    return String(value ?? "")
        .replace(/&/g, "&amp;")
        .replace(/</g, "&lt;")
        .replace(/>/g, "&gt;")
        .replace(/"/g, "&quot;")
        .replace(/'/g, "&#039;");
}
function safeAttribute(value) {
    return safe(value);
}
/* =====================================================
   START
===================================================== */
document.getElementById(
    "year"
).textContent =
    new Date().getFullYear();
loadPortfolio();
</script>
</body>
</html>