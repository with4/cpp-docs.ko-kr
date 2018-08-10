---
title: ref new, gcnew (c + + 구성 요소 확장) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs:
- C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ed742d3762232846b2cac189978ea07c140b65f2
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012659"
---
# <a name="ref-new-gcnew--c-component-extensions"></a>ref new, gcnew(C++ 구성 요소 확장)
합니다 **ref n e w** 집계 키워드는 가비지 수집 개체에 액세스할 수 없을 때 핸들을 반환 하는 형식의 인스턴스가 할당 ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) 할당된 된 개체에 있습니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 할당 된 형식의 인스턴스에 대 한 메모리 **ref n e w** 자동으로 할당이 취소 됩니다.  
  
 A **ref n e w** 작업이 throw `OutOfMemoryException` 메모리를 할당할 수 없는 경우.  
  
 네이티브 c + + 형식에 대 한 메모리를 할당 하 고 할당 취소 하는 방법에 대 한 자세한 내용은 참조 하세요. [새 및 delete 연산자](../cpp/new-and-delete-operators.md)합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 사용 하 여 **ref n e w** 수명을 자동으로 관리 하려는 Windows 런타임 개체에 대 한 메모리를 할당할 수 있습니다. 참조 개수가 0이 되면 개체는 자동으로 할당 취소되며, 참조의 마지막 복사본이 범위를 벗어난 후에 발생합니다. 자세한 내용은 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/ZW`  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 에 의해 관리 되는 형식 (참조 또는 값 형식)에 대 한 메모리 할당 되었습니다 **gcnew**, 고 가비지 수집을 사용 하 여 할당을 취소 합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: `/clr`  
  
### <a name="examples"></a>예제  
  
 다음 예제에서는 **gcnew** 메시지 개체를 할당 합니다.  
  
```cpp  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 다음 예제에서는 **gcnew** 참조 형식 처럼 사용할 boxed 값 형식인을 만들려고 합니다.  
  
```cpp  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
```Output  
32  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)