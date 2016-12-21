---
title: "COleVariant Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "자동화, 매개 변수 형식"
  - "COleVariant class"
  - "VARIANT data type"
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

캡슐화는  [변형](http://msdn.microsoft.com/ko-kr/e305240e-9e11-4006-98cc-26f4932d2118) 데이터 형식입니다.  
  
## 구문  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleVariant::COleVariant](../Topic/COleVariant::COleVariant.md)|`COleVariant` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleVariant::Attach](../Topic/COleVariant::Attach.md)|첨부는  **변형** 에 있는 `COleVariant`.|  
|[COleVariant::ChangeType](../Topic/COleVariant::ChangeType.md)|Variant 형식을 변경 `COleVariant` 개체입니다.|  
|[COleVariant::Clear](../Topic/COleVariant::Clear.md)|이 `COleVariant` 개체를 지웁니다.|  
|[COleVariant::Detach](../Topic/COleVariant::Detach.md)|분리는  **변형** 에서 `COleVariant` 및 반환의  **변형**.|  
|[COleVariant::GetByteArrayFromVariantArray](../Topic/COleVariant::GetByteArrayFromVariantArray.md)|바이트 배열은 기존 variant 배열에서 검색합니다.|  
|[COleVariant::SetString](../Topic/COleVariant::SetString.md)|특정 형식에 일반적으로 ANSI 문자열을 설정합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[COleVariant::operator LPCVARIANT](../Topic/COleVariant::operator%20LPCVARIANT.md)|변환 된 `COleVariant` 값으로 `LPCVARIANT`.|  
|[COleVariant::operator LPVARIANT](../Topic/COleVariant::operator%20LPVARIANT.md)|변환 된 `COleVariant` 개체에 `LPVARIANT`.|  
|[COleVariant::operator \=](../Topic/COleVariant::operator%20=.md)|복사본은 `COleVariant` 값입니다.|  
|[COleVariant::operator \=\=](../Topic/COleVariant::operator%20==.md)|두 비교 `COleVariant` 값입니다.|  
|[COleVariant::operator \<\<, \>\>](../Topic/COleVariant::operator%20%3C%3C,%20%3E%3E.md)|Outputs a `COleVariant` value to `CArchive` or `CDumpContext` and inputs a `COleVariant` object from `CArchive`.|  
  
## 설명  
 이 데이터 형식은 OLE 자동화에 사용 됩니다.  구체적으로 [DISPPARAMS](http://msdn.microsoft.com/ko-kr/a16e5a21-766e-4287-b039-13429aa78f8b) 구조에 대 한 포인터의 배열 포함  **변형** 구조.  A  **DISPPARAMS** 구조에 대 한 매개 변수를 전달 하는 데 사용 [IDispatch::Invoke](http://msdn.microsoft.com/ko-kr/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
> [!NOTE]
>  이 클래스에서 파생 되는  **변형** 구조.  즉 전달 하면는 `COleVariant` 호출 매개 변수에서는  **변형** 와의 데이터 멤버는  **변형** 구조에 있는 데이터를 액세스할 수 있는 멤버의 `COleVariant`.  
  
 두 MFC 클래스와 관련 된  [COleCurrency](../../mfc/reference/colecurrency-class.md) 및  [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) variant 데이터 형식을 캡슐화  **통화** \(`VT_CY`\)와  **날짜** \(`VT_DATE`\).  `COleVariant` 클래스가 사용 됩니다 광범위 하 게 DAO 클래스에 있습니다. 예를 들어이 클래스의 일반적인 사용법에 대 한 이러한 클래스를 참조 하십시오  [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 및  [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 자세한 내용은  [변형](http://msdn.microsoft.com/ko-kr/e305240e-9e11-4006-98cc-26f4932d2118),  [통화](http://msdn.microsoft.com/ko-kr/5e81273c-7289-45c7-93c0-32c1553f708e), [DISPPARAMS](http://msdn.microsoft.com/ko-kr/a16e5a21-766e-4287-b039-13429aa78f8b), 및 [IDispatch::Invoke](http://msdn.microsoft.com/ko-kr/964ade8e-9d8a-4d32-bd47-aa678912a54d) 항목에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 에 대 한 자세한 내용은 `COleVariant` 클래스에서 OLE 자동화를 사용 하 고 문서에서 "전달 매개 변수를 OLE 자동화"를 참조 하십시오.  [자동화](../../mfc/automation.md).  
  
## 상속 계층 구조  
 `tagVARIANT`  
  
 `COleVariant`  
  
## 요구 사항  
 **헤더:**  afxdisp.h  
  
## 참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)