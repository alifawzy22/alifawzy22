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





actions: [
        Container(
          margin:const EdgeInsets.only(
            //right: 16,
          ),
          child: PopupMenuButton(
            //icon: Icon(Icons.arrow_circle_down_outlined,size: 40,),
            itemBuilder: (context){
              return [
                    PopupMenuItem(
                        value: 'profile',
                        child: Row(
                          mainAxisAlignment: MainAxisAlignment.spaceBetween,
                          children:const [
                            Text('الملف الشخصي',style: TextStyle(
                              fontWeight: FontWeight.bold,
                              fontSize: 15,
                              color: Color(0xFF005578),
                            ),),
                            Icon(Icons.person_rounded,color: Colors.blue,size: 30,),
                          ],
                        ),
                        onTap: (){
                          print("Profile Tapped");
                        },
                    ),
                    PopupMenuItem(
                        value: 'profile',
                        child: Row(
                          mainAxisAlignment: MainAxisAlignment.spaceBetween,
                          children:const [
                            Text('تواصل معنا',style: TextStyle(
                              fontWeight: FontWeight.bold,
                              fontSize: 15,
                              color: Color(0xFF005578),
                            ),),
                            Icon(Icons.contact_mail_rounded,color: Colors.blue,size: 30,),
                          ],
                        ),
                        onTap: () {
                          print('Contact Tapped');
                        },
                    ),

                    
                ];
            },
            onSelected:(value){
              if(value == 0){
                  print("My account menu is selected.");
              }else if(value == 1){
                  print("Settings menu is selected.");
              }else if(value == 2){
                  print("Logout menu is selected.");
              }
            }
          ),
        ),

        ],
      


