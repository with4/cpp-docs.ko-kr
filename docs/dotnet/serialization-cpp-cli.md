---
title: Serialization (C + + /cli CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f4a410da74c37ee722c04f21e2cde906b9d061d2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="serialization-ccli"></a>Serialization(C++/CLI)
Serialization (개체 또는 멤버를 영구적인 매체에의 상태를 저장할 경우의 프로세스)의 관리 클래스 (개별 필드 또는 속성 포함)에서 지원 되는 <xref:System.SerializableAttribute> 및 <xref:System.NonSerializedAttribute> 클래스입니다.  
  
## <a name="remarks"></a>설명  
 적용 된 **SerializableAttribute** 전체 클래스를 serialize 하거나에 특정 필드 또는 관리 되는 클래스의 부분을 직렬화 할 속성을 적용 하는 관리 되는 클래스를 사용자 지정 특성입니다. 사용 하 여는 **NonSerializedAttribute** 제외 필드 또는 관리 되는 클래스의 속성을 serialize 하 고에서 사용자 지정 특성입니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 클래스에에서 `MyClass` (속성과 `m_nCount`) 직렬화 가능으로 표시 됩니다. 그러나는 `m_nData` 나타내듯이 속성은 serialize 되지 않습니다는 **NonSerialized** 사용자 지정 특성:  
  
### <a name="code"></a>코드  
  
```  
// serialization_and_mcpp.cpp  
// compile with: /LD /clr  
using namespace System;  
  
[ Serializable ]  
public ref class MyClass {  
public:  
   int m_nCount;  
private:  
   [ NonSerialized ]  
   int m_nData;  
};  
```  
  
### <a name="comments"></a>설명  
 두 특성 모두 "약식 이름"을 사용 하 여 참조할 수 있는지 확인 (**Serializable** 및 **NonSerialized**). 자세한 내용은에서 [특성 적용](/dotnet/standard/attributes/applying-attributes)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)