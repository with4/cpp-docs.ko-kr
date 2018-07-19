---
title: '방법: 정의 및 전역 예외 처리기 설치 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b77e982e3668ca23ece2eeeb5c609d71b30dc908
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33129686"
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>방법: 전역 예외 처리기 정의 및 설치
다음 코드 예제에서는 어떻게 처리 되지 않은 예외를 보여 줍니다. 캡처할 수 있습니다. 폼 예제는 단추를 포함 하는를 누를 때 예외를 throw 하는 null 참조를 수행 합니다. 이 기능은 일반적인 코드 오류를 나타냅니다. Main 함수에 의해 설치 된 응용 프로그램 수준 예외 핸들러에서 예외가 발생 검색 되었습니다.  
  
 대리자를 바인딩하여 이렇게는 <xref:System.Windows.Forms.Application.ThreadException> 이벤트입니다. 이 경우 후속 예외 전송 됩니다는 `App::OnUnhandled` 메서드.  
  
## <a name="example"></a>예제  
  
```  
// global_exception_handler.cpp  
// compile with: /clr  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Threading;  
using namespace System::Drawing;  
using namespace System::Windows::Forms;  
  
ref class MyForm : public Form  
{  
   Button^ b;  
public:  
   MyForm( )  
   {  
      b = gcnew Button( );  
      b->Text = "Do Null Access";  
      b->Size = Drawing::Size(150, 30);  
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);  
      Controls->Add(b);  
   }  
   void OnClick(Object^ sender, EventArgs^ args)   
   {  
      // do something illegal, like call through a null pointer...  
      Object^ o = nullptr;  
      o->ToString( );        
   }  
};  
  
ref class App  
{  
public:  
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)  
   {  
      MessageBox::Show(e->Exception->Message, "Global Exeception");  
      Application::ExitThread( );  
   }  
};  
  
int main()  
{  
   Application::ThreadException += gcnew   
      ThreadExceptionEventHandler(App::OnUnhandled);  
  
   MyForm^ form = gcnew MyForm( );  
   Application::Run(form);  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [예외 처리](../windows/exception-handling-cpp-component-extensions.md)