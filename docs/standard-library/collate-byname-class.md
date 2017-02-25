---
title: "collate_byname 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::collate_byname"
  - "locale/std::collate_byname"
  - "std.collate_byname"
  - "collate_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collate_byname 클래스"
ms.assetid: 3dc380df-867c-4763-b60e-ba62a8e63ca7
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# collate_byname 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된 로캘의 데이터 정렬 패싯으로 사용할 수 있는 개체를 설명하는 파생된 템플릿 클래스입니다. 이 클래스를 사용하여 문자열 정렬 규약과 관련된 문화 영역별 정보를 검색할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```
template <class CharType>
class collate_byname : public collate<CharType> {
public:
    explicit collate_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit collate_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~collate_byname();

};
```  
  
#### <a name="parameters"></a>매개 변수  
 `_Locname`  
 명명 된 로캘입니다.  
  
 `_Refs`  
 초기 참조 횟수입니다.  
  
## <a name="remarks"></a>주의  
 로 사용할 수 있는 개체를 설명 하는 템플릿 클래스는 [로캘 패싯](../standard-library/locale-class.md#facet_class) 형식의 [collate](../standard-library/collate-class.md#collate__collate)\< CharType>합니다. 해당 동작은 의해 결정 되는 [라는](../standard-library/locale-class.md#locale__name) 로캘 `_Locname`합니다. 각 생성자와 해당 기본 개체를 초기화 합니다. [collate](../standard-library/collate-class.md#collate__collate)\< CharType>( `_Refs`).  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \< 로캘>  
  
 **네임 스페이스:** std  
  
## <a name="see-also"></a>참고 항목  
 [C + + 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)



