# SoundCheckerSwiftUI

import SwiftUI
import AudioToolbox

struct Item: Identifiable {
    var id = UUID()
    let soundCode: Int
}
struct ContentView: View {
    let items: [Item] = [
        Item(soundCode: 1000), Item(soundCode: 1001), Item(soundCode: 1002), Item(soundCode: 1003), Item(soundCode: 1004), Item(soundCode: 1005), Item(soundCode: 1006), Item(soundCode: 1007), Item(soundCode: 1008), Item(soundCode: 1009), Item(soundCode: 1010), Item(soundCode: 1011), Item(soundCode: 1012), Item(soundCode: 1013), Item(soundCode: 1014), Item(soundCode: 1015), Item(soundCode: 1016), Item(soundCode: 1020), Item(soundCode: 1021), Item(soundCode: 1022), Item(soundCode: 1023), Item(soundCode: 1024), Item(soundCode: 1025), Item(soundCode: 1026), Item(soundCode: 1027), Item(soundCode: 1028), Item(soundCode: 1029), Item(soundCode: 1030), Item(soundCode: 1031), Item(soundCode: 1032), Item(soundCode: 1033), Item(soundCode: 1034), Item(soundCode: 1035), Item(soundCode: 1036), Item(soundCode: 1050), Item(soundCode: 1051), Item(soundCode: 1052), Item(soundCode: 1053), Item(soundCode: 1054), Item(soundCode: 1055), Item(soundCode: 1057), Item(soundCode: 1070), Item(soundCode: 1071), Item(soundCode: 1072), Item(soundCode: 1073), Item(soundCode: 1074), Item(soundCode: 1075), Item(soundCode: 1100), Item(soundCode: 1101), Item(soundCode: 1102), Item(soundCode: 1103), Item(soundCode: 1104), Item(soundCode: 1105), Item(soundCode: 1106), Item(soundCode: 1107), Item(soundCode: 1108), Item(soundCode: 1109), Item(soundCode: 1110), Item(soundCode: 1111), Item(soundCode: 1112), Item(soundCode: 1113), Item(soundCode: 1114), Item(soundCode: 1115), Item(soundCode: 1116), Item(soundCode: 1117), Item(soundCode: 1118), Item(soundCode: 1150), Item(soundCode: 1151), Item(soundCode: 1152), Item(soundCode: 1153), Item(soundCode: 1154), Item(soundCode: 1200), Item(soundCode: 1201), Item(soundCode: 1202), Item(soundCode: 1203), Item(soundCode: 1204), Item(soundCode: 1205), Item(soundCode: 1206), Item(soundCode: 1207), Item(soundCode: 1208), Item(soundCode: 1209), Item(soundCode: 1210), Item(soundCode: 1211), Item(soundCode: 1254), Item(soundCode: 1255), Item(soundCode: 1256), Item(soundCode: 1257), Item(soundCode: 1258), Item(soundCode: 1259), Item(soundCode: 1300), Item(soundCode: 1301), Item(soundCode: 1302), Item(soundCode: 1303), Item(soundCode: 1304), Item(soundCode: 1305), Item(soundCode: 1306), Item(soundCode: 1307), Item(soundCode: 1308), Item(soundCode: 1309), Item(soundCode: 1310), Item(soundCode: 1311), Item(soundCode: 1312), Item(soundCode: 1313), Item(soundCode: 1314), Item(soundCode: 1315), Item(soundCode: 1320), Item(soundCode: 1321), Item(soundCode: 1322), Item(soundCode: 1323), Item(soundCode: 1324), Item(soundCode: 1325), Item(soundCode: 1326), Item(soundCode: 1327), Item(soundCode: 1328), Item(soundCode: 1329), Item(soundCode: 1330), Item(soundCode: 1331), Item(soundCode: 1332), Item(soundCode: 1333), Item(soundCode: 1334), Item(soundCode: 1335), Item(soundCode: 1336), Item(soundCode: 1350), Item(soundCode: 1351), Item(soundCode: 4095)
    ]
    
    var body: some View {
        List(items) { item in
            Text(String(item.soundCode))
                .gesture(TapGesture().onEnded({ _ in
                    AudioServicesPlayAlertSound(SystemSoundID(item.soundCode))
                }))
        }
        .frame(minWidth: 0, maxWidth: .infinity, minHeight: 0, maxHeight: .infinity)
        .padding(.top)
    }
}

struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
