### Hi there 👋

<!--
**alifawzy22/alifawzy22** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
void uploadFileToServer(File imagePath) async {
  var request = new http.MultipartRequest(
      "POST", Uri.parse('your api url her'));
request.fields['name'] = 'Rohan';
request.fields['title'] = 'My first image';
request.files.add(await http.MultipartFile.fromPath('profile_pic', imagePath.path));
  request.send().then((response) {
    http.Response.fromStream(response).then((onValue) {
      try {
        // get your response here...
      } catch (e) {
        // handle exeption
      }
    });
  });
}
