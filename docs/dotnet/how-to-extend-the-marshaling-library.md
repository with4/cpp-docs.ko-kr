---
title: "방법: 마샬링 라이브러리 확장명 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ee919e1faa37959d25e8e42581c8cde80d640337
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-extend-the-marshaling-library"></a>방법: 마샬링 라이브러리 확장명
이 데이터 형식 사이 더 많은 변환을 수 있도록 마샬링 라이브러리를 확장 하는 방법을 설명 합니다. 사용자는 현재 지원 하지 않는 라이브러리에서 데이터 변환에 대 한 마샬링 라이브러리를 확장할 수 있습니다.  
  
 여부에 관계 없이 두 가지 방법 중 하나에 마샬링 라이브러리를 확장할 수 있습니다는 [marshal_context 클래스](../dotnet/marshal-context-class.md)합니다. 검토는 [개요의 c + + 마샬링](../dotnet/overview-of-marshaling-in-cpp.md) 새 변환을 컨텍스트가 필요 여부를 결정 하는 항목입니다.  
  
 두 경우 모두, 먼저 새 마샬링 변환에 대 한 파일을 만듭니다. 이렇게 하면 표준 마샬링 라이브러리 파일의 무결성을 유지 합니다. 프로젝트 또는 다른 프로그래머를 다른 컴퓨터로 이식 하려는 경우에 나머지 프로젝트와 함께 새 마샬링 파일을 복사 해야 합니다. 이러한 방식으로 프로젝트를 받은 사용자 새 변환을 수신 하도록 보장할 수 및 라이브러리 파일을 수정 하지 않아도 됩니다.  
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>컨텍스트를 필요 하지 않은 변환을 마샬링 라이브러리를 확장 하려면  
  
1.  예를 들어 MyMarshal.h 새로운 마샬링 작업을 저장할 파일을 만듭니다.  
  
2.  마샬링 라이브러리 파일 중 하나 이상 포함 합니다.  
  
    -   기본 형식에 대 한 marshal.h 합니다.  
  
    -   windows 데이터 형식에 대 한 marshal_windows.h 합니다.  
  
    -   c + + 표준 라이브러리 데이터 형식에 대 한 marshal_cppstd.h 합니다.  
  
    -   ATL 데이터 형식에 대 한 marshal_atl.h 합니다.  
  
3.  이러한 단계의 끝에 코드를 사용 하 여 변환 함수를 작성 합니다. 이 코드에서는 TO는, FROM에서 변환 하는 형식이 고 `from` 변환할 매개 변수입니다.  
  
4.  변환 하는 코드로 변환 논리에 대 한 주석을 바꿉니다는 `from` to 개체에 대 한 매개 변수 입력 하 고 변환 된 개체를 반환 합니다.  
  
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
  
### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>컨텍스트를 필요로 하는 변환을 마샬링 라이브러리 확장명  
  
1.  예를 들어 MyMarshal.h 새로운 마샬링 작업을 저장할 파일 만들기  
  
2.  마샬링 라이브러리 파일 중 하나 이상 포함 합니다.  
  
    -   기본 형식에 대 한 marshal.h 합니다.  
  
    -   windows 데이터 형식에 대 한 marshal_windows.h 합니다.  
  
    -   c + + 표준 라이브러리 데이터 형식에 대 한 marshal_cppstd.h 합니다.  
  
    -   ATL 데이터 형식에 대 한 marshal_atl.h 합니다.  
  
3.  이러한 단계의 끝에 코드를 사용 하 여 변환 함수를 작성 합니다. 이 코드에서는 TO는, FROM에서 변환 하는 형식이 `toObject` 하면 결과 저장 하는 포인터 및 `fromObject` 변환할 매개 변수입니다.  
  
4.  초기화 코드를 사용 하 여 초기화 하는 방법에 대 한 주석을 `toPtr` 을 적절 한 빈 값입니다. 예를 들어 대 한 포인터인 경우로 설정 `NULL`합니다.  
  
5.  변환 논리에 대 한 주석을 변환 하는 코드로 바꿉니다는 `from` 매개 변수 개체로 *TO* 유형입니다. 이 변환 된 개체에 저장 될 `toPtr`합니다.  
  
6.  설정에 대 한 주석을 `toObject` 설정 하는 코드와 `toObject` 변환 된 개체에 있습니다.  
  
7.  할당 한 메모리를 확보 하는 코드를 사용 하 여 네이티브 리소스를 정리 하는 방법에 대 한 주석을 `toPtr`합니다. 경우 `toPtr` 할당 된 메모리를 사용 하 여 `new`를 사용 하 여 `delete` 메모리를 해제 합니다.  
  
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
  
## <a name="example"></a>예  
 다음 예제는 컨텍스트를 필요 하지 않은 변환을 마샬링 라이브러리를 확장 합니다. 이 예제에서는 코드 네이티브 데이터 형식에서 직원 정보를 관리 되는 데이터 형식으로 변환합니다.  
  
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
  
 이전 예에서 `marshal_as` 함수 변환 된 데이터에 대 한 핸들을 반환 합니다. 이 작업은 데이터의 추가 복사본 생성을 방지 하기 위해 수행 되었습니다. 변수를 직접 반환은 불필요 한 성능 비용 관련 된 합니다.  
  
```Output  
Managed name: Jeff Smith  
Managed address: 123 Main Street  
Managed zip code: 98111  
```  
  
## <a name="example"></a>예  
 다음 예제에서는 네이티브 데이터 형식으로 관리 되는 데이터 형식에서 직원 정보를 변환합니다. 이 변환은 마샬링 컨텍스트가 필요합니다.  
  
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
  
```Output  
Native name: Jeff Smith  
Native address: 123 Main Street  
Native zip code: 98111  
```  
  
## <a name="see-also"></a>참고 항목  
 [C++ 마샬링 개요](../dotnet/overview-of-marshaling-in-cpp.md)