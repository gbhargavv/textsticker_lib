
Android Text Sticker
===========================

A Library which can add sticker with zoom, drag, flip, delete functions.

Usage
=====
* In your app you add Text Sticker by using below code.
```java
 
 DisplayMetrics displayMetrics = new DisplayMetrics();
        getWindowManager().getDefaultDisplay().getMetrics(displayMetrics);
        canvasHeight = displayMetrics.heightPixels;
        canvasWidth = displayMetrics.widthPixels;

  Font font = new Font();
        font.setColor(getResources().getColor(R.color.black));
        font.setSize(0.075f);
        createTextStickView(0, "My Sticker", font, this.canvasWidth / 2, this.canvasHeight / 2,
                0.0f, 1.0f, 0, 0, Layout.Alignment.ALIGN_CENTER, 255, false, false, 0.0f, 10.0f);
```
```
private void createTextStickView(int i, String str, Font font, int i2, int i3, float f, float f2, int i4, int i5,
                                     Layout.Alignment alignment, int i6, boolean z, boolean z2, float f3, float f4) {
        this.textSticker = new TextStickerView(this, this.canvasWidth, this.canvasHeight);
        RelativeLayout.LayoutParams layoutParams = new RelativeLayout.LayoutParams(-2, -2);
        layoutParams.addRule(10);
        this.textSticker.setLayoutParams(layoutParams);
        this.textSticker.setText(str);
        this.textSticker.setLayoutX(i2);
        this.textSticker.setLayoutY(i3);
        this.textSticker.setRotateAngle(f);
        this.textSticker.setScale(f2);
        this.textSticker.setPaddingLeft(i4);
        this.textSticker.setPaddingRight(i5);
        this.textSticker.setFont(font);
        this.textSticker.setAlign(alignment);
        this.textSticker.setOpacity(i6);
        this.textSticker.setUnderLine(z);
        this.textSticker.setStrikethrough(z2);
        this.textSticker.setLetterSpacing(f3);
        this.textSticker.setLineSpacing(f4);
        this.textSticker.setTag(Integer.valueOf(i));
        this.textSticker.setOperationListener(new TextStickerView.OperationListener() {
            public void onUnselect(TextStickerView textStickerView) {
            }

            public void onDelete(TextStickerView textStickerView) {
                frameLayout.removeView(textSticker);
                frameLayout.requestLayout();
            }

            public void onEdit(TextStickerView textStickerView) {
                if (textStickerView.isInEditMode())
                    textStickerView.setInEdit(false);
                else textStickerView.setInEdit(true);
            }

            public void onTouch(TextStickerView textStickerView) {

            }

            public void onSelect(TextStickerView textStickerView) {
                textSticker.setInEdit(true);
                textSticker.setShowHelpBox(true);
            }
        });
        frameLayout.addView(textSticker);
        frameLayout.requestLayout();
    }
```


Download
========

      implementation 'com.github.gbhargavv:textsticker_lib:v1.2'

<a href="https://www.buymeacoffee.com/gbhargavv" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png" alt="Buy Me A Coffee" style="height: 50px !important;width: 200px !important;box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;-webkit-box-shadow: 0px 3px 2px 0px rgba(190, 190, 190, 0.5) !important;" ></a>

## Example

<img src="https://github.com/gbhargavv/Custom-Text-Sticker/blob/master/image/Record_2023-08-02-09-53-32.gif" align="left" width="30%">

