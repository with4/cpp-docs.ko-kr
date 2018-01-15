---
title: "ref new, gcnew (c + + 구성 요소 확장명) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs: C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 616117f7274d6f68456aa23614fb354a71982fb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="ref-new-gcnew--c-component-extensions"></a>ref new, gcnew(C++ 구성 요소 확장)
`ref new` 핸들을 반환 하 고 개체에 액세스할 수 없을 때 가비지가 수집 되는 형식의 인스턴스를 할당 하는 집계 키워드 ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md))에 할당 된 개체입니다.  
  
## <a name="all-runtimes"></a>모든 런타임  
 `ref new`에서 할당한 형식의 인스턴스에 대한 메모리가 자동으로 할당 취소됩니다.  
  
 메모리를 할당할 수 없는 경우 `ref new` 작업에서 `OutOfMemoryException`이 throw됩니다.  
  
 네이티브 c + + 형식에 대 한 메모리를 할당 하 고 할당 취소 하는 방법에 대 한 자세한 내용은 참조 [새 및 delete 연산자](../cpp/new-and-delete-operators.md)합니다.  
  
## <a name="windows-runtime"></a>Windows 런타임  
 `ref new`를 사용하여 수명을 자동으로 관리하려는 Windows 런타임 개체에 대한 메모리를 할당할 수 있습니다. 참조 개수가 0이 되면 개체는 자동으로 할당 취소되며, 참조의 마지막 복사본이 범위를 벗어난 후에 발생합니다. 자세한 내용은 참조 [Ref 클래스 및 구조체](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx)합니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/ZW**  
  
## <a name="common-language-runtime"></a>공용 언어 런타임 
 관리되는 형식(참조 또는 값 형식)에 대한 메모리는 `gcnew`에 의해 할당되고 가비지 수집을 사용하여 할당 취소됩니다.  
  
### <a name="requirements"></a>요구 사항  
 컴파일러 옵션: **/clr**  
  
### <a name="examples"></a>예제  
 **예제**  
  
 다음 예제에서는 `gcnew`를 사용하여 Message 개체를 할당합니다.  
  
```  
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
  
 **예제**  
  
 다음 예제에서는 `gcnew`를 사용하여 참조 형식처럼 사용할 boxed 값 형식을 만듭니다.  
  
```  
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
  
 **출력**  
  
```Output  
32  
```  
  
## <a name="see-also"></a>참고 항목  
 [런타임 플랫폼용 구성 요소 확장](../windows/component-extensions-for-runtime-platforms.md)