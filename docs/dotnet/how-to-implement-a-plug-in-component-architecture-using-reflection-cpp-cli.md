---
title: "방법: 리플렉션을 사용하여 플러그 인 구성 요소 아키텍처 구현(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "플러그인[C++]"
  - "리플렉션[C++}, 플러그 인"
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 리플렉션을 사용하여 플러그 인 구성 요소 아키텍처 구현(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 코드 예제에서는 리플렉션을 사용하여 간단한 "플러그 인" 아키텍처를 구현하는 방법을 보여 줍니다.  코드의 첫 번째 부분은 응용 프로그램이고 두 번째 부분은 플러그 인입니다.  이 응용 프로그램은 명령줄 인수로 지정된 플러그 인 DLL에 있는 폼 기반 클래스를 사용하여 내용을 채우는 다중 문서 폼입니다.  
  
 이 응용 프로그램은 제공된 어셈블리를 <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> 메서드를 사용하여 로드합니다.  어셈블리가 제대로 로드되면 어셈블리 내에 있는 형식을 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> 메서드를 사용하여 열거합니다.  그런 다음 <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> 메서드를 사용하여 각 형식의 호환성 여부를 검사합니다.  이 예제의 경우 제공된 어셈블리에 있는 클래스는 플러그 인 역할을 위해 <xref:System.Windows.Forms.Form> 클래스에서 파생되어야 합니다.  
  
 호환되는 클래스는 <xref:System.Type>을 인수로 사용하고 새 인스턴스에 대한 포인터를 반환하는 <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> 메서드를 사용하여 인스턴스화됩니다.  그런 다음 각각의 새 인스턴스가 폼에 연결되고 표시됩니다.  
  
 <xref:System.Reflection.Assembly.Load%2A> 메서드에 사용되는 어셈블리 이름에는 파일 확장명이 포함되지 않습니다.  응용 프로그램의 주 함수는 제공되는 모든 확장명을 트리밍하므로 다음 코드 예제는 두 경우 모두 작동합니다.  
  
## 예제  
 다음 코드에서는 플러그 인을 사용하는 응용 프로그램을 정의합니다.  어셈블리 이름은 첫 번째 인수로 제공해야 합니다.  이 어셈블리에는 public <xref:System.Windows.Forms.Form> 파생 형식이 적어도 하나 이상 포함되어야 합니다.  
  
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
  
## 예제  
 다음 코드에서는 <xref:System.Windows.Forms.Form>에서 파생된 클래스 세 개를 정의합니다.  결과 어셈블리의 이름을 위 응용 프로그램 코드의 실행 파일에 전달하면 컴파일할 때 이러한 세 클래스가 호스팅 응용 프로그램에 알려져 있지 않더라도 각 클래스가 검색 및 인스턴스화됩니다.  
  
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
  
## 참고 항목  
 [리플렉션](../dotnet/reflection-cpp-cli.md)