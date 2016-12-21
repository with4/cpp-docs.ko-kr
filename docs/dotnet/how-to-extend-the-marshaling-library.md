---
title: "방법: 마샬링 라이브러리 확장 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "마샬링 라이브러리, 확장"
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
caps.latest.revision: 27
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 마샬링 라이브러리 확장
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 항목에서는 마샬링 라이브러리를 확장하여 데이터 형식 사이에 더 많은 변환을 제공하는 방법을 설명합니다.  사용자는 라이브러리에서 현재 지원되지 않는 데이터 변환에 대해 마샬링 라이브러리를 확장할 수 있습니다.  
  
 [marshal\_context 클래스](../dotnet/marshal-context-class.md)를 사용하거나 사용하지 않는 두 가지 방법 중에서 하나로 마샬링 라이브러리를 확장할 수 있습니다.  새 변환에 컨텍스트가 필요한지 여부를 확인하려면 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md) 항목을 검토하십시오.  
  
 두 경우 모두 먼저 새 마샬링 변환을 위한 파일을 만듭니다.  이는 표준 마샬링 라이브러리 파일의 무결성을 보존하기 위한 것입니다.  프로젝트를 다른 컴퓨터 또는 다른 프로그래머에게 이식하려면 새 마샬링 파일을 프로젝트 나머지 부분과 함께 복사해야 합니다.  이렇게 하면 프로젝트를 받는 사용자가 새 변환을 확실히 받게 되므로 라이브러리 파일을 수정할 필요가 없습니다.  
  
### 컨텍스트가 필요 없는 변환으로 마샬링 라이브러리를 확장하려면  
  
1.  새 마샬링 함수를 저장할 파일을 만듭니다\(예: MyMarshal.h\).  
  
2.  다음과 같은 마샬 라이브러리 파일을 하나 이상 포함합니다.  
  
    -   기본 형식을 위한 marshal.h  
  
    -   Windows 데이터 형식을 위한 marshal\_windows.h  
  
    -   STL 데이터 형식을 위한 marshal\_cppstd.h  
  
    -   ATL 데이터 형식을 위한 marshal\_atl.h  
  
3.  이 단계의 끝에 있는 코드를 사용하여 변환 함수를 작성합니다.  이 코드에서 TO는 변환된 후의 형식이고 FROM은 변환되기 전의 형식입니다. `from`은 변환될 매개 변수입니다.  
  
4.  변환 논리에 대한 주석을 `from` 매개 변수를 TO 형식의 개체로 변환하고 변환된 개체를 반환하는 코드로 바꿉니다.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      inline TO marshal_as<TO, FROM> (const FROM& from) {  
         // Insert conversion logic here, and return a TO parameter.  
      }  
   }  
}  
```  
  
### 컨텍스트가 필요한 변환으로 마샬링 라이브러리를 확장하려면  
  
1.  새 마샬링 함수를 저장할 파일을 만듭니다\(예: MyMarshal.h\).  
  
2.  다음과 같은 마샬 라이브러리 파일을 하나 이상 포함합니다.  
  
    -   기본 형식을 위한 marshal.h  
  
    -   Windows 데이터 형식을 위한 marshal\_windows.h  
  
    -   STL 데이터 형식을 위한 marshal\_cppstd.h  
  
    -   ATL 데이터 형식을 위한 marshal\_atl.h  
  
3.  이 단계의 끝에 있는 코드를 사용하여 변환 함수를 작성합니다.  이 코드에서 TO는 변환된 후의 형식이고 FROM은 변환되기 전의 형식입니다. `toObject`는 결과를 저장할 포인터이고, `fromObject`는 변환될 매개 변수입니다.  
  
4.  초기화에 대한 주석을 `toPtr`을 적절한 빈 값으로 초기화하는 코드로 바꿉니다.  예를 들어 포인터인 경우에는 `NULL`로 설정합니다.  
  
5.  Replace the comment about conversion logic with code to convert the `from` parameter into an object of *TO* type.  이 변환된 개체는 `toPtr`에 저장됩니다.  
  
6.  `toObject` 설정에 대한 주석을 `toObject`를 변환된 개체로 설정하는 코드로 바꿉니다.  
  
7.  네이티브 리소스 지우기에 대한 주석을 `toPtr`에 할당된 메모리를 비우는 코드로 바꿉니다.  `toPtr`가 `new`를 사용하여 메모리를 할당한 경우에는 `delete`를 사용하여 메모리를 비웁니다.  
  
```  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<TO, FROM> : public context_node_base  
      {  
      private:  
         TO toPtr;  
      public:  
         context_node(TO& toObject, FROM fromObject)  
         {  
            // (Step 4) Initialize toPtr to the appropriate empty value.  
            // (Step 5) Insert conversion logic here.  
            // (Step 6) Set toObject to the converted parameter.  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // (Step 7) Clean up native resources.  
         }  
      };  
   }  
}   
```  
  
## 예제  
 다음 예제는 컨텍스트가 필요 없는 변환으로 마샬링 라이브러리를 확장합니다.  이 예제에서 코드는 직원 정보를 네이티브 데이터 형식에서 관리되는 데이터 형식으로 변환합니다.  
  
```  
// MyMarshalNoContext.cpp  
// compile with: /clr  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   char* name;  
   char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      inline ManagedEmp^ marshal_as<ManagedEmp^, NativeEmp> (const NativeEmp& from) {  
         ManagedEmp^ toValue = gcnew ManagedEmp;  
         toValue->name = marshal_as<System::String^>(from.name);  
         toValue->address = marshal_as<System::String^>(from.address);  
         toValue->zipCode = from.zipCode;  
         return toValue;  
      }  
   }  
}  
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {   
   NativeEmp employee;  
  
   employee.name = "Jeff Smith";  
   employee.address = "123 Main Street";  
   employee.zipCode = 98111;  
  
   ManagedEmp^ result = marshal_as<ManagedEmp^>(employee);  
  
   Console::WriteLine("Managed name: {0}", result->name);  
   Console::WriteLine("Managed address: {0}", result->address);  
   Console::WriteLine("Managed zip code: {0}", result->zipCode);  
  
   return 0;  
}  
```  
  
 이전 예제에서 `marshal_as` 함수는 변환된 데이터에 대한 핸들을 반환합니다.  이는 데이터의 추가 복사본이 작성되는 것을 방지하기 위해 수행된 것입니다.  변수를 직접 반환하면 이와 관련하여 불필요한 성능 비용이 발생합니다.  
  
  **Managed name: Jeff Smith**  
**Managed address: 123 Main Street**  
**Managed zip code: 98111**   
## 예제  
 다음 예제에서는 직원 정보를 관리되는 데이터 형식에서 네이티브 데이터 형식으로 변환합니다.  이 변환에는 마샬링 컨텍스트가 필요합니다.  
  
```  
// MyMarshalContext.cpp  
// compile with: /clr  
#include <stdlib.h>  
#include <string.h>  
#include <msclr/marshal.h>  
  
value struct ManagedEmp {  
   System::String^ name;  
   System::String^ address;  
   int zipCode;  
};  
  
struct NativeEmp {  
   const char* name;  
   const char* address;  
   int zipCode;  
};  
  
namespace msclr {  
   namespace interop {  
      template<>  
      ref class context_node<NativeEmp*, ManagedEmp^> : public context_node_base  
      {  
      private:  
         NativeEmp* toPtr;  
         marshal_context context;  
      public:  
         context_node(NativeEmp*& toObject, ManagedEmp^ fromObject)  
         {  
            // Conversion logic starts here  
            toPtr = NULL;  
  
            const char* nativeName;  
            const char* nativeAddress;  
  
            // Convert the name from String^ to const char*.  
            System::String^ tempValue = fromObject->name;  
            nativeName = context.marshal_as<const char*>(tempValue);  
  
            // Convert the address from String^ to const char*.  
            tempValue = fromObject->address;  
            nativeAddress = context.marshal_as<const char*>(tempValue);  
  
            toPtr = new NativeEmp();  
            toPtr->name = nativeName;  
            toPtr->address = nativeAddress;  
            toPtr->zipCode = fromObject->zipCode;  
  
            toObject = toPtr;  
         }  
         ~context_node()  
         {  
            this->!context_node();  
         }  
      protected:  
         !context_node()  
         {  
            // When the context is deleted, it will free the memory  
            // allocated for toPtr->name and toPtr->address, so toPtr  
            // is the only memory that needs to be freed.  
            if (toPtr != NULL) {  
               delete toPtr;  
               toPtr = NULL;  
            }  
         }  
      };  
   }  
}   
  
using namespace System;  
using namespace msclr::interop;  
  
int main() {  
   ManagedEmp^ employee = gcnew ManagedEmp();  
  
   employee->name = gcnew String("Jeff Smith");  
   employee->address = gcnew String("123 Main Street");  
   employee->zipCode = 98111;  
  
   marshal_context context;  
   NativeEmp* result = context.marshal_as<NativeEmp*>(employee);  
  
   if (result != NULL) {  
      printf_s("Native name: %s\nNative address: %s\nNative zip code: %d\n",  
         result->name, result->address, result->zipCode);  
   }  
  
   return 0;  
}  
```  
  
  **Native name: Jeff Smith**  
**Native address: 123 Main Street**  
**Native zip code: 98111**   
## 참고 항목  
 [C\+\+ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)