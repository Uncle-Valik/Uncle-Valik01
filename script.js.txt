document.getElementById("avatarInput").addEventListener("change", function(event) {
    const file = event.target.files[0];
    if (file) {
        const reader = new FileReader();
        reader.onload = function(e) {
            document.getElementById("avatarPreview").src = e.target.result;
        };
        reader.readAsDataURL(file);
    }
});

const photoInputs = [1, 2, 3].map(num => document.getElementById(`photoInput${num}`));
const photoPreviews = [1, 2, 3].map(num => document.getElementById(`photoPreview${num}`));

photoInputs.forEach((input, index) => {
    input.addEventListener("change", function(event) {
        const file = event.target.files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = function(e) {
                photoPreviews[index].src = e.target.result;
            };
            reader.readAsDataURL(file);
        }
    });
});
