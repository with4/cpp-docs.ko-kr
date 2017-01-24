---
title: "컬렉션 | Microsoft Docs"
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
  - "배열 템플릿"
  - "배열[C++], 클래스"
  - "컬렉션 클래스, 컬렉션 클래스 정보"
  - "컬렉션 클래스, 배열"
  - "컬렉션 클래스, 목록"
  - "컬렉션 클래스, 맵"
  - "컬렉션 클래스, MFC"
  - "컬렉션 클래스, 도형"
  - "컬렉션 클래스, 템플릿 기반"
  - "컬렉션, 컬렉션 정보"
  - "MFC 컬렉션 클래스"
  - "MFC, 컬렉션"
  - "도형"
  - "도형, 컬렉션"
ms.assetid: 02586e4c-851d-41d0-a722-feb11c17c74c
caps.latest.revision: 18
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 컬렉션
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation 클래스 라이브러리는 개체 그룹을 관리 하는 컬렉션 클래스를 제공 합니다.  이 클래스는 두 가지 유형입니다.  
  
-   [C \+ \+ 템플릿에서 생성 된 컬렉션 클래스](#_core_the_template.2d.based_collection_classes)  
  
-   [C \+ \+ 템플릿에서 생성 되지 않은 컬렉션 클래스](#_core_the_collection_classes_not_based_on_templates)  
  
> [!NOTE]
>  코드에서 이미 비템플릿 기반 컬렉션 클래스를 사용 하는 경우을 사용 하 여 계속할 수 있습니다.  사용자 지정 데이터 형식에 대 한 새로운 형식 안전 컬렉션 클래스를 작성 하는 경우 새로운 템플릿 기반 클래스를 사용 하는 것이 좋습니다.  
  
##  <a name="_core_collection_shapes"></a> 컬렉션 모양  
 컬렉션 클래스의 "형태" 및 해당 요소의 형식 규정 됩니다.  도형 개체는 구성하고 컬렉션에 저장 하는 방법을 참조합니다.  MFC는 세 가지 기본 컬렉션 모양: 목록, 배열, 및 \(사전\)에 매핑합니다.  특정 프로그래밍 문제에 가장 적합 한 컬렉션 모양을 선택할 수 있습니다.  
  
 세 개의 도형에 제공 된 컬렉션의 각이 항목의 뒷부분에 간략하게 설명 되어 있습니다.  프로그램에 가장 적합 한 결정 하는 데 도움이 도형 기능 비교를 참조 하십시오. [컬렉션 클래스 선택에 대한 권장 사항](../mfc/recommendations-for-choosing-a-collection-class.md).  
  
-   List  
  
     List 클래스는 이중 연결된 목록으로 구현 된 요소의 순서가, 인덱스 되지 않은 목록을 제공 합니다.  "머리"와 "꼬리"가 목록과 매우 빠르게가 머리 또는 꼬리 또는 삽입 하거나 삭제할 요소에서에서 요소를 제거 하거나 추가 합니다.  
  
-   배열  
  
     Array 클래스는 개체의 크기, 정렬, 및 정수 인덱스 동적 배열을 제공합니다.  
  
-   맵 \(사전\)  
  
     맵을 값 개체를 사용 하 여 키 개체를 연결 하는 컬렉션입니다.  
  
##  <a name="_core_the_template.2d.based_collection_classes"></a> 템플릿 기반 컬렉션 클래스  
 모든 형식의 개체를 포함 하는 형식 안전 컬렉션을 구현 하는 가장 쉬운 방법은 MFC 템플릿 기반 클래스 중 하나를 사용 하는 것.  이러한 클래스의 예제를 보려면 MFC 샘플을 [수집](../top/visual-cpp-samples.md)합니다.  
  
 다음 표에서 MFC 템플릿 기반 컬렉션 클래스를 나열합니다.  
  
### 템플릿 및 컬렉션 클래스  
  
|컬렉션 내용|배열|목록|맵|  
|------------|--------|--------|-------|  
|무작위 형식 개체의 컬렉션입니다.|`CArray`|`CList`|`CMap`|  
|모든 형식의 개체에 대 한 포인터 컬렉션|`CTypedPtrArray`|`CTypedPtrList`|`CTypedPtrMap`|  
  
##  <a name="_core_the_collection_classes_not_based_on_templates"></a> 비템플릿 기반 컬렉션 클래스  
 코드에서 이미 MFC비템플릿 기반 컬렉션 클래스를 사용 하는 경우을 사용 하 여 계속할 수 있습니다.  그러나 새 컬렉션 템플릿 기반 클래스를 사용 하는 것이 좋습니다.  다음 표에서 비템플릿 기반 MFC 컬렉션 클래스입니다.  
  
### 템플릿 및 비 템플릿 컬렉션 클래스  
  
|배열|목록|맵|  
|--------|--------|-------|  
|`CObArray`|`CObList`|`CMapPtrToWord`|  
|`CByteArray`|`CPtrList`|`CMapPtrToPtr`|  
|`CDWordArray`|`CStringList`|`CMapStringToOb`|  
|`CPtrArray`||`CMapStringToPtr`|  
|`CStringArray`||`CMapStringToString`|  
|`CWordArray`||`CMapWordToOb`|  
|`CUIntArray`||`CMapWordToPtr`|  
  
 MFC 컬렉션 클래스 특성 테이블에 [컬렉션 클래스 선택에 대한 권장 사항](../mfc/recommendations-for-choosing-a-collection-class.md) \(도형\)이 아닌 이러한 특성의 관점에서 MFC 컬렉션 클래스에 설명 합니다.  
  
-   클래스는 c \+ \+ 템플릿을 사용 하 여 여부  
  
-   요소는 컬렉션에 저장 된 serialize 할 수 있는지 여부  
  
-   여부 진단에 대 한 컬렉션에 저장 된 요소를 덤프 될 수 있습니다.  
  
-   컬렉션 형식 인지 여부  
  
### 수행할 작업  
  
#### 일반 컬렉션 클래스 작업  
  
-   [컬렉션 클래스 선택에 대한 권장 사항](../mfc/recommendations-for-choosing-a-collection-class.md)  
  
-   [방법: 형식이 안전한 컬렉션 만들기](../mfc/how-to-make-a-type-safe-collection.md)  
  
-   [스택 및 큐 컬렉션 만들기](../mfc/creating-stack-and-queue-collections.md)  
  
-   [CArray::Add](../Topic/CArray::Add.md)  
  
#### 템플릿 기반 컬렉션 클래스  
  
-   [템플릿 기반 클래스](../mfc/template-based-classes.md)  
  
#### 컬렉션의 멤버에 액세스 \(템플릿 기반 여부\)  
  
-   [컬렉션의 모든 멤버에 액세스](../mfc/accessing-all-members-of-a-collection.md)  
  
-   [CObject 컬렉션의 모든 개체 삭제](../mfc/deleting-all-objects-in-a-cobject-collection.md)  
  
## 참고 항목  
 [개념](../mfc/mfc-concepts.md)   
 [일반 MFC 항목](../mfc/general-mfc-topics.md)