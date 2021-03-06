---
title: "FIELD_MODIFIERS |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FIELD_MODIFIERS
helpviewer_keywords: FIELD_MODIFIERS enumeration
ms.assetid: 1e44681c-1f03-41a9-9c04-b79f231b0822
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 98f6e4d3f187261bcf9c0d1ad3959093d864e222
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2017
---
# <a name="fieldmodifiers"></a>FIELD_MODIFIERS
指定的欄位型別修飾詞。  
  
## <a name="syntax"></a>語法  
  
```cpp  
enum enum_FIELD_MODIFIERS {   
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
typedef DWORD FIELD_MODIFIERS;  
```  
  
```csharp  
public enum enum_FIELD_MODIFIERS {  
   FIELD_MOD_NONE             = 0x00000000,  
  
   // Modifier of the field  
   FIELD_MOD_ACCESS_NONE      = 0x00000001,  
   FIELD_MOD_ACCESS_PUBLIC    = 0x00000002,  
   FIELD_MOD_ACCESS_PROTECTED = 0x00000004,  
   FIELD_MOD_ACCESS_PRIVATE   = 0x00000008,  
  
   // Storage modifier of the field  
   FIELD_MOD_NOMODIFIERS      = 0x00000010,  
   FIELD_MOD_STATIC           = 0x00000020,  
   FIELD_MOD_CONSTANT         = 0x00000040,  
   FIELD_MOD_TRANSIENT        = 0x00000080,  
   FIELD_MOD_VOLATILE         = 0x00000100,  
   FIELD_MOD_ABSTRACT         = 0x00000200,  
   FIELD_MOD_NATIVE           = 0x00000400,  
   FIELD_MOD_SYNCHRONIZED     = 0x00000800,  
   FIELD_MOD_VIRTUAL          = 0x00001000,  
   FIELD_MOD_INTERFACE        = 0x00002000,  
   FIELD_MOD_FINAL            = 0x00004000,  
   FIELD_MOD_SENTINEL         = 0x00008000,  
   FIELD_MOD_INNERCLASS       = 0x00010000,  
   FIELD_TYPE_OPTIONAL        = 0x00020000,  
   FIELD_MOD_BYREF            = 0x00040000,  
   FIELD_MOD_HIDDEN           = 0x00080000,  
   FIELD_MOD_MARSHALASOBJECT  = 0x00100000,  
   FIELD_MOD_SPECIAL_NAME     = 0x00200000,  
   FIELD_MOD_HIDEBYSIG        = 0x00400000,  
  
   FIELD_MOD_WRITEONLY        = 0x80000000,  
   FIELD_MOD_ACCESS_MASK      = 0x000000ff,  
   FIELD_MOD_MASK             = 0xffffff00,  
   FIELD_MOD_ALL              = 0x7fffffff  
};  
```  
  
## <a name="members"></a>成員  
 FIELD_MOD_ACCESS_TYPE  
 表示無法存取該欄位。  
  
 FIELD_MOD_ACCESS_PUBLIC  
 表示欄位具有公用存取。  
  
 FIELD_MOD_ACCESS_PROTECTED  
 表示具有保護存取欄位。  
  
 FIELD_MOD_ACCESS_PRIVATE  
 表示欄位具有私用存取。  
  
 FIELD_MOD_NOMODIFIERS  
 指出欄位具有任何修飾詞。  
  
 FIELD_MOD_STATIC  
 指出欄位為靜態。  
  
 FIELD_MOD_CONSTANT  
 表示欄位是常數。  
  
 FIELD_MOD_TRANSIENT  
 表示欄位是暫時性的。  
  
 FIELD_MOD_VOLATILE  
 表示欄位是暫時性。  
  
 FIELD_MOD_ABSTRACT  
 表示欄位是抽象的。  
  
 FIELD_MOD_NATIVE  
 表示欄位是原生。  
  
 FIELD_MOD_SYNCHRONIZED  
 表示欄位同步處理。  
  
 FIELD_MOD_VIRTUAL  
 表示欄位是虛擬的。  
  
 FIELD_MOD_INTERFACE  
 表示欄位是一種介面。  
  
 FIELD_MOD_FINAL  
 表示最後欄位。  
  
 FIELD_MOD_SENTINEL  
 表示欄位是 sentinel。  
  
 FIELD_MOD_INNERCLASS  
 表示欄位是內部的類別。  
  
 FIELD_TYPE_OPTIONAL  
 表示此欄位為選擇性。  
  
 FIELD_MOD_BYREF  
 表示欄位的參考引數。 這是特別針對方法引數。  
  
 FIELD_MOD_HIDDEN  
 表示欄位必須隱藏或顯示在另一個內容;例如，[!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]靜態區域變數。  
  
 FIELD_MOD_MARSHALASOBJECT  
 表示欄位代表的物件`IUnknown`介面。  
  
 FIELD_MOD_SPECIAL_NAME  
 表示欄位具有特殊的名稱，例如`.ctor`的建構函式 ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]只)。  
  
 FIELD_MOD_HIDEBYSIG  
 表示欄位具有`Overloads`套用至它的關鍵字 ([!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)]只)。  
  
 FIELD_MOD_WRITEONLY  
 表示欄位是唯寫。 此值不會納入`FIELD_MOD_ALL`，因為這類的唯寫的欄位只能使用適用於函式評估。 使用者必須明確要求提供`FIELD_MOD_WRITEONLY`欄位。  
  
 FIELD_MOD_ACCESS_MASK  
 表示欄位存取權的遮罩。  
  
 FIELD_MOD_MASK  
 表示欄位修飾詞的遮罩。  
  
## <a name="remarks"></a>備註  
 用於`dwModifiers`隸屬[FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)結構。  
  
 這些值也會傳遞給[EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)來篩選特定欄位的方法。  
  
## <a name="requirements"></a>需求  
 標頭： sh.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 組件： Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>請參閱  
 [列舉型別](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [FIELD_INFO](../../../extensibility/debugger/reference/field-info.md)   
 [EnumFields](../../../extensibility/debugger/reference/idebugcontainerfield-enumfields.md)