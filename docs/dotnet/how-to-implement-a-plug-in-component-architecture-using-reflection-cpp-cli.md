---
title: 플러그 인 아키텍처 구현 (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- plug-ins [C++]
- reflection [C++}, plug-ins
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4e001ef88af0727a994c309d45167787d3e6677b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33135215"
---
# <a name="how-to-implement-a-plug-in-component-architecture-using-reflection-ccli"></a>방법: 리플렉션을 사용하여 플러그 인 구성 요소 아키텍처 구현(C++/CLI)
다음 코드 예제는 간단한 "플러그 인" 아키텍처를 구현 하는 리플렉션 사용을 보여 줍니다. 첫 번째 부분은 응용 프로그램을이 고 두 번째 플러그 인 합니다. 응용 프로그램에 명령줄 인수로 제공 되는 플러그 인 DLL에는 양식 기반 클래스를 사용 하 여 자신을 채우는 여러 문서 형태입니다.  
  
 응용 프로그램에서 사용 하 여 제공 된 어셈블리를 로드 하려고는 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드. 성공 하는 경우 사용 하 여 어셈블리 내의 형식이 열거는 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> 메서드. 각 형식에 다음 사용 하 여 호환성에 대 한 확인란이 <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> 메서드. 이 예제에서는 제공 된 어셈블리의 클래스에서 파생 되어야 합니다는 <xref:System.Windows.Forms.Form> 클래스는 플러그 인으로 처리 합니다.  
  
 호환 되는 클래스는 사용 하 여 인스턴스화됩니다는 <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> 메서드를 허용 하는 <xref:System.Type> 인수로 서 새 인스턴스에 대 한 포인터를 반환 합니다. 그런 다음 각각의 새 인스턴스에 폼에 연결 되 고 표시 합니다.  
  
 <xref:System.Reflection.Assembly.Load%2A> 메서드는 파일 확장명을 포함 하는 어셈블리 이름을 허용 하지 않습니다. 다음 코드 예제에서는 두 경우 모두에서 작동 하므로 응용 프로그램의 주 기능은 제공 된 모든 확장을 삭제 합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 응용 프로그램에서는 플러그 인을 정의 합니다. 어셈블리 이름이 첫 번째 인수로 제공 되어야 합니다. 이 어셈블리에는 public이 하나 이상 포함 해야 <xref:System.Windows.Forms.Form> 파생 형식입니다.  
  
```  
// plugin_application.cpp  
// compile with: /clr /c  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
  
ref class PluggableForm : public Form  {  
public:  
   PluggableForm() {}  
   PluggableForm(Assembly^ plugAssembly) {  
      Text = "plug-in example";  
      Size = Drawing::Size(400, 400);  
      IsMdiContainer = true;  
  
      array<Type^>^ types = plugAssembly->GetTypes( );  
      Type^ formType = Form::typeid;  
  
      for (int i = 0 ; i < types->Length ; i++) {  
         if (formType->IsAssignableFrom(types[i])) {  
            // Create an instance given the type description.  
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));  
            if (f) {  
               f->Text = types[i]->ToString();  
               f->MdiParent = this;  
               f->Show();  
            }  
         }  
      }  
   }  
};  
  
int main() {  
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");  
   Application::Run(gcnew PluggableForm(a));  
}  
```  
  
## <a name="example"></a>예제  
 다음 코드에서 파생 된 세 개의 클래스를 정의 <xref:System.Windows.Forms.Form>합니다. 결과 어셈블리 이름의 이름을 이전 샘플의 실행 파일에 전달 될 때 각 세 가지 클래스는 검색 되며도 컴파일 타임에 호스팅 응용 프로그램에 알려진 모든 것을 인스턴스화할 합니다.  
  
```  
// plugin_assembly.cpp  
// compile with: /clr /LD  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
using namespace System::Drawing;  
  
public ref class BlueForm : public Form {  
public:  
   BlueForm() {  
      BackColor = Color::Blue;  
   }  
};  
  
public ref class CircleForm : public Form {  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);  
   }  
};  
  
public ref class StarburstForm : public Form {  
public:  
   StarburstForm(){  
      BackColor = Color::Black;  
   }  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      Pen^ p = gcnew Pen(Color::Red, 2);  
      Random^ r = gcnew Random( );  
      Int32 w = ClientSize.Width;  
      Int32 h = ClientSize.Height;  
      for (int i=0; i<100; i++) {  
         float x1 = w / 2;  
         float y1 = h / 2;  
         float x2 = r->Next(w);  
         float y2 = r->Next(h);  
         args->Graphics->DrawLine(p, x1, y1, x2, y2);  
      }  
   }  
};  
```  
  
## <a name="see-also"></a>참고 항목  
 [리플렉션(C++/CLI)](../dotnet/reflection-cpp-cli.md)