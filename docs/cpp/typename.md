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
ms.openlocfilehash: b6eebf038fbe3e5e18e3f2a1e8e7a2aa2554bf41
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="typename"></a>typename
템플릿 정의에 알 수 없는 식별자 형식임을 컴파일러 힌트를 제공 합니다. 템플릿 매개 변수 목록에서 형식 매개 변수를 지정 하는 데 사용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
typename identifier;  
```  
  
## <a name="remarks"></a>설명  
 템플릿 정의에 이름이 템플릿 인수;에 종속 된 정규화 된 이름을 경우이 키워드를 사용 해야 합니다. 정규화 된 이름이 종속 된 경우 선택 사항입니다. 자세한 내용은 참조 [템플릿 및 이름 확인](../cpp/templates-and-name-resolution.md)합니다.  
  
 **typename** 템플릿 선언 또는 정의에 있는 형식에서 사용할 수 있습니다. 템플릿 기본 클래스의 템플릿 인수로 사용되지 않는 한 기본 클래스 목록에서는 허용되지 않습니다.  
  
```  
template <class T>  
class C1 : typename T::InnerType // Error - typename not allowed.  
{};  
template <class T>  
class C2 : A<typename T::InnerType>  // typename OK.  
{};  
```  
  
 **typename** 키워드 대신 사용할 수도 있습니다 **클래스** 템플릿 매개 변수 목록입니다. 예를 들어 다음 문은 의미상 동일합니다.  
  
```  
template<class T1, class T2>...  
template<typename T1, typename T2>...  
```  
  
## <a name="example"></a>예제  
  
```  
// typename.cpp  
template<class T> class X  
{  
   typename T::Y m_y;   // treat Y as a type  
};  
  
int main()  
{  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [서식 파일](../cpp/templates-cpp.md)   
 [키워드](../cpp/keywords-cpp.md)