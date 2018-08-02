---
title: typename | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- typename_cpp
dev_langs:
- C++
helpviewer_keywords:
- typename template specifier
ms.assetid: 52e1d901-220d-4f0d-ab43-dae7e05fb491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 79ba7d0bda73762d04f0dd11668eb31c275ac03f
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467931"
---
# <a name="typename"></a>typename
템플릿 정의에 알 수 없는 식별자 형식 인지 컴파일러에 힌트를 제공 합니다. 템플릿 매개 변수 목록의 형식 매개 변수 지정에 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
typename identifier;  
```  
  
## <a name="remarks"></a>설명  
 템플릿 정의에서 이름을 정규화 된 이름 템플릿 인수;에 종속 된 경우이 키워드를 사용 해야 정규화 된 이름이 종속 하는 경우 선택 사항입니다. 자세한 내용은 [템플릿 및 이름 확인](../cpp/templates-and-name-resolution.md)합니다.  
  
 **typename** 템플릿 선언 또는 정의에 어디서 나 모든 형식에서 사용할 수 있습니다. 템플릿 기본 클래스의 템플릿 인수로 사용되지 않는 한 기본 클래스 목록에서는 허용되지 않습니다.  
  
```cpp 
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 합니다 **typename** 키워드 대신 사용할 수도 있습니다 **클래스** 템플릿 매개 변수에서를 나열 합니다. 예를 들어 다음 문은 기능적으로 동일합니다.  
  
```cpp 
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>예  
  
```cpp 
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>참고자료  
 [템플릿](../cpp/templates-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)