---
title: '방법: 이미지가 네이티브 인지 CLR 인지 확인 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common language runtime, image testing
- images [C++], CLR verification
- /clr compiler option [C++], detecting use in compilation
- common language runtime, /clr compiler option
ms.assetid: 5a854822-6172-4b22-b236-320165412568
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 71b13c1f82f233589102c72ed08a731db7de5c56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33128227"
---
# <a name="how-to-determine-if-an-image-is-native-or-clr"></a>방법: 이미지가 네이티브인지 CLR인지 확인
공용 언어 런타임을 사용 하는 것에 대 한 이미지 빌드 되었는지 여부를 결정 하는 한 가지 방법은 **dumpbin**[/CLRHEADER](../build/reference/clrheader.md)합니다.  
  
 또한 프로그래밍 방식으로 이미지를 공용 언어 런타임에 대 한 빌드 되었는지 여부를 확인할 수 있습니다. 자세한 내용은 참조 [하는 방법: /clr 컴파일 감지](../dotnet/how-to-detect-clr-compilation.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 공용 언어 런타임에서 실행 되도록 이미지 빌드 되었는지 여부를 결정 합니다.  
  
```  
// detect_image_type.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
enum class CompilationMode {Invalid, Native, CLR };  
  
static CompilationMode IsManaged(String^ filename) {  
   try {  
      array<Byte>^ data = gcnew array<Byte>(4096);  
      FileInfo^ file = gcnew FileInfo(filename);  
      Stream^ fin = file->Open(FileMode::Open, FileAccess::Read);  
      Int32 iRead = fin->Read(data, 0, 4096);  
      fin->Close();  
  
      // Verify this is a executable/dll  
      if ((data[1] << 8 | data[0]) != 0x5a4d)  
         return CompilationMode::Invalid;  
  
      // This will get the address for the WinNT header  
      Int32 iWinNTHdr = data[63]<<24 | data[62]<<16 | data[61] << 8 | data[60];  
  
      // Verify this is an NT address  
      if ((data[iWinNTHdr+3] << 24 | data[iWinNTHdr+2] << 16 | data[iWinNTHdr+1] << 8 | data[iWinNTHdr]) != 0x00004550)  
         return CompilationMode::Invalid;  
  
      Int32 iLightningAddr = iWinNTHdr + 24 + 208;  
      Int32 iSum = 0;  
      Int32 iTop = iLightningAddr + 8;  
  
      for (int i = iLightningAddr; i < iTop; ++i)  
         iSum |= data[i];  
  
      if (iSum == 0)  
         return CompilationMode::Native;  
      else  
         return CompilationMode::CLR;  
   }  
   catch(Exception ^e) {  
      throw(e);  
   }  
}  
  
int main() {  
   array<String^>^ args = Environment::GetCommandLineArgs();  
  
   if (args->Length < 2) {  
      Console::WriteLine("USAGE : detect_clr <assembly_name>\n");  
      return -1;  
   }  
  
   Console::WriteLine("{0} is compiled {1}", args[1], IsManaged(args[1]));  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ Interop 사용(암시적 PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)