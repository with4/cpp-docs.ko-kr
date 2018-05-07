---
title: '방법: 클립보드에 텍스트 저장 (C + + /cli CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- text, storing in Clipboard
- Clipboard, storing text
ms.assetid: 9996023f-b700-47ad-8ad9-1ba201eaa5a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9ac33eb31dbda97d3c695847344cd857d2e77675
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-store-text-in-the-clipboard-ccli"></a>방법: 클립보드에 텍스트 저장(C++/CLI)
다음 코드 예제에서는 <xref:System.Windows.Forms.Clipboard> 에 정의 된 개체는 <xref:System.Windows.Forms> 네임 스페이스 문자열을 저장 합니다. 이 개체는 두 개의 멤버 함수를 제공: <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> 및 <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>합니다. 데이터에서 파생 된 개체를 전송 하 여 클립보드에 저장 됩니다 <xref:System.Object> 를 <xref:System.Windows.Forms.Clipboard.SetDataObject%2A>합니다.  
  
## <a name="example"></a>예제  
  
```  
// store_clipboard.cpp  
// compile with: /clr  
#using <System.dll>  
#using <System.Drawing.dll>  
#using <System.Windows.Forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main()  
{  
   String^ str = "This text is copied into the Clipboard.";  
  
   // Use 'true' as the second argument if  
   // the data is to remain in the clipboard  
   // after the program terminates.  
   Clipboard::SetDataObject(str, true);  
  
   Console::WriteLine("Added text to the Clipboard.");  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [방법: 클립보드에서 텍스트 검색 (C + + /cli CLI)](../dotnet/how-to-retrieve-text-from-the-clipboard-cpp-cli.md)   
 [Windows 작업 (C + + /cli CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)