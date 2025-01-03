# Ttw-JS--DrawSVGAPI

---

# 문의 사항

- thdtjsdn@gmail.com

---

# SVG Draw API 입니다.

- 많은 다량의 랜더링을 고려하여 성능 위주의 코드로 작성 되었습니다.

---

# 본 API는 '무료제공' 입니다.

- 자유롭게 사용하셔도 무방합니다.

---

# Sample source

- Example link
	- http://thdtjsdn.com:49310/app_tool/html_page/DrawSVG/index.html

```javascript
const CANVAS = TAPI.ge('ID-CANVAS');
const WEBGL = CANVAS.getContext('webgl');

const EVENT_LISTENERS = {

	Clear: function () {
		APIS.clearRect(SVG);
	}
	, Arc: function () {
		APIS.drawArc(SVG
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random()
			, getArc_Random() * Math.PI / 2, Math.PI, false
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Circle: function () {
		APIS.drawCircle(SVG
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, getX_Random(), getY_Random(), getRadius_Random()
		);
		APIS.drawCircle_Fill(SVG, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getX_Random(), getY_Random(), getRadius_Random());
		APIS.drawCircle_Line(SVG, 5, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getX_Random(), getY_Random(), getRadius_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Rect: function () {
		APIS.drawRect(SVG
			, getX_Random(), getY_Random()
			, getX_Random() / 8, getY_Random() / 8
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		APIS.drawRect_Fill(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		APIS.drawRect_Line(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Line: function () {
		APIS.drawLine(SVG
			, getX_Random(), getY_Random(), getX_Random(), getY_Random()
			, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, LineGradient: function () {
		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawLine_Gradient(SVG
			, getX_Random(), getY_Random(), getX_Random(), getY_Random()
			, getLineWidth_Random(), colorStops
		);

		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Polygon: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygon(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolygonGradientLinear: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }

		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawPolygon_Gradient_Linear(SVG, a, colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolygonGradientLinearCenter: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }

		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawPolygon_Gradient_Linear_Center(SVG, a, colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Polygon_Dashed_NN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygon_Dashed(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Polygon_Dashed_NNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygon_Dashed(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Polygon_Dashed_NNNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygon_Dashed(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, PolygonBezierCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygonBezierCurve(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolygonCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolygonCurve(SVG, a, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	//----------------------------------------------------------------------------------------------------;

	, Polyline: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline(SVG, a, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineGradientLinear: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }

		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawPolyline_Gradient_Linear(SVG, a, getLineWidth_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineGradientLinearCenter: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }

		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawPolyline_Gradient_Linear_Center(SVG, a, getLineWidth_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Polyline_Dashed_NN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Polyline_Dashed_NNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, Polyline_Dashed_NNNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, PolylineBezierCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineBezierCurve(SVG, a, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineBezierCurve_Dashed_NN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineBezierCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolylineBezierCurve_Dashed_NNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineBezierCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolylineBezierCurve_Dashed_NNNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineBezierCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, PolylineCurve: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurve(SVG, a, getLineWidth_Random(), APIS_RANDOM_HEXCOLOR(), getAlpha_Random());
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, PolylineCurve_Dashed_NN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolylineCurve_Dashed_NNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, PolylineCurve_Dashed_NNNN: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolylineCurve_Dashed(SVG, a, getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, [getDashed_Random(), getDashed_Random(), getDashed_Random(), getDashed_Random()]
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, PolylinePressureFront: function () {
		var a = [];
		var i = 0, iLen = APIS_RANDOM_NUMBER(5, 10);
		for (; i < iLen; ++i) { a.push(getX_Random(), getY_Random()); }
		APIS.drawPolyline__PressureFront(SVG, 2, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), a, 20);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, RegularPolygon: function () {
		APIS.drawRegularPolygon(SVG
			, getX_Random(), getY_Random(), getRadius_Random(), getSides_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, RegularPolygonGradientLinear: function () {
		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];

		APIS.drawRegularPolygon_Gradient_Linear(SVG, getX_Random(), getY_Random(), getRadius_Random(), getSides_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, RegularPolygonRotation: function () {
		APIS.drawRegularPolygon_Rotation(SVG
			, getX_Random(), getY_Random(), getRadius_Random(), getSides_Random(), getRotation_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random(), getLineWidth_Random()
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, GradientCircular: function () {
		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];
		APIS.drawGradient_Circular(SVG, getX_Random(), getY_Random(), getRadius_Random(), getRadius_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	, GradientLinear: function () {
		var colorStops = [
			0.0, APIS_RANDOM_HEXCOLOR(),
			0.5, APIS_RANDOM_HEXCOLOR(),
			1.0, APIS_RANDOM_HEXCOLOR()
		];
		APIS.drawGradient_Linear(SVG, getX_Random(), getY_Random(), getX_Random(), getY_Random(), colorStops);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Bitmap: function () {
		var bitmap;
		function drawImage(bitmap) {
			APIS.drawImageBitmap(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, bitmap); // 이미지 객체, x 좌표, y 좌표, 너비, 높이
			if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(function () { drawImage(bitmap); }); }
		}
		const url = 'http://thdtjsdn.com:49310/app_thdtjsdn/html_page/Resume/index.photo.png';
		TAPI.w.apis.xhr.getResponseBlob(url, function (e) {
			bitmap = URL.createObjectURL(e.target.response);
			drawImage(bitmap);
		});
	}
	, BitmapRotation: function () {
		var bitmap;
		function drawImage(bitmap) {
			APIS.drawImageBitmap_Rotation(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, getRotationStyle_Random(), bitmap); // 비트맵 객체, x 좌표, y 좌표, 너비, 높이, 45도 회전
			if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(function () { drawImage(bitmap); }); }
		}
		const url = 'http://thdtjsdn.com:49310/app_thdtjsdn/html_page/Resume/index.photo.png';
		TAPI.w.apis.xhr.getResponseBlob(url, function (e) {
			bitmap = URL.createObjectURL(e.target.response);
			drawImage(bitmap);
		});
	}

	, Image: function () {
		const URL = 'http://thdtjsdn.com:49310/app_thdtjsdn/html_page/Resume/index.photo.png';
		APIS.drawImage(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, URL); // 이미지 객체, x 좌표, y 좌표, 너비, 높이
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, ImageRotation: function () {
		const URL = 'http://thdtjsdn.com:49310/app_thdtjsdn/html_page/Resume/index.photo.png';
		APIS.drawImage_Rotation(SVG, getX_Random(), getY_Random(), getX_Random() / 8, getY_Random() / 8, getRotationStyle_Random(), URL); // 이미지 객체, x 좌표, y 좌표, 너비, 높이
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}

	//----------------------------------------------------------------------------------------------------;

	, Text: function () {
		APIS.drawText(SVG
			, getX_Random(), getY_Random()
			, 'THDTJSDN', getFontSize_Random() + 'px', 'Arial'
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, TextRotation: function () {
		APIS.drawText_Rotation(SVG
			, getX_Random(), getY_Random()
			, 'THDTJSDN', getFontSize_Random() + 'px', 'Arial'
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, getRotationStyle_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, TextLine: function () {
		APIS.drawText_Line(SVG
			, getX_Random(), getY_Random()
			, 'THDTJSDN', getFontSize_Random() + 'px', 'Arial'
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
	, TextLineRotation: function () {
		APIS.drawText_Line_Rotation(SVG
			, getX_Random(), getY_Random()
			, 'THDTJSDN', getFontSize_Random() + 'px', 'Arial'
			, APIS_RANDOM_HEXCOLOR(), getAlpha_Random()
			, getRotationStyle_Random()
		);
		if (TAPI.gec('ID-CHECKBOX--CONTINUE-CREATE')) { requestAnimationFrame(arguments.callee); }
	}
};
```

---

# API 목록(필요할 법한 목록만)

 - clearRect = function (parentElement)

 - drawArc = function (parentElement, fillStyle, globalAlpha_Fill, lineWidth, strokeStyle, globalAlpha_Line, cX, cY, r, sA, eA, counterClockWise)
 - drawArc_Fill = function (parentElement, fillStyle, globalAlpha_Fill, cX, cY, r, sA, eA, counterClockWise)
 - drawArc_Line = function (t, lineWidth, strokeStyle, globalAlpha, cX, cY, r, sA, eA, counterClockWise)

 - drawCircle = function (parentElement, fillStyle, globalAlpha_Fill, lineWidth, strokeStyle, globalAlpha_Line, cX, cY, r)
 - drawCircle_Fill = function (parentElement, fillStyle, globalAlpha, cX, cY, r)
 - drawCircle_Line = function (parentElement, lineWidth, strokeStyle, globalAlpha, cX, cY, r)

 - drawGradient_Circular = function (parentElement, cX, cY, innerRadius, outerRadius, colorStops)
 - drawGradient_Linear = function (parentElement, x0, y0, x1, y1, colorStops)

 - drawImage = function (parentElement, x, y, width, height, imageUrl)
 - drawImage_Rotation = function (parentElement, x, y, width, height, rotationAngle, imageUrl)
 - drawImageBitmap = function (parentElement, x, y, width, height, bitmap)
 - drawImageBitmap_Rotation = function (parentElement, x, y, width, height, rotationAngle, bitmapUrl)

 - drawLine = function (parentElement, x1, y1, x2, y2, lineWidth, strokeStyle, globalAlpha)
 - drawLine_Gradient = function (parentElement, x1, y1, x2, y2, lineWidth, gradientStops)

 - drawPolygon = function (parentElement, points, fillStyle, globalAlpha_Fill, lineWidth, strokeStyle, globalAlpha_Line)
 - drawPolygonBezierCurve = function (parentElement, points, fillStyle, globalAlpha_Fill, lineWidth, strokeStyle, globalAlpha_Line)
 - drawPolygonCurve = function (parentElement, points, fillStyle, globalAlpha_Fill, lineWidth, strokeStyle, globalAlpha_Line)
 - drawPolygon_Dashed = function (parentElement, points, fillStyle, globalAlpha_Fill, lineWidth, strokeStyle, globalAlpha_Line, dashArray)
 - drawPolygon_Gradient_Linear = function (parentElement, points, gradientStops)
 - drawPolygon_Gradient_Linear_Center = function (parentElement, points, gradientStops)

 - drawPolyline = function (parentElement, points, lineWidth, strokeStyle, globalAlpha)
 - drawPolylineBezierCurve = function (parentElement, points, lineWidth, strokeStyle, globalAlpha)
 - drawPolylineBezierCurve_Dashed = function (parentElement, points, lineWidth, strokeStyle, globalAlpha, dashArray)
 - drawPolylineCurve = function (parentElement, points, lineWidth, strokeStyle, globalAlpha)
 - drawPolylineCurve_Dashed = function (parentElement, points, lineWidth, strokeStyle, globalAlpha, dashArray)
 - drawPolyline_Dashed = function (parentElement, points, lineWidth, strokeStyle, globalAlpha, dashArray)
 - drawPolyline_Gradient_Linear = function (parentElement, points, lineWidth, gradientStops)
 - drawPolyline_Gradient_Linear_Center = function (parentElement, points, lineWidth, gradientStops)

 - drawRect = function (parentElement, x, y, width, height, fillStyle, globalAlpha_Fill, lineWidth, strokeStyle, globalAlpha_Line)
 - drawRect_Fill = function (parentElement, x, y, width, height, fillStyle, globalAlpha_Fill)
 - drawRect_Line = function (parentElement, lineWidth, strokeStyle, globalAlpha, x, y, width, height)

 - drawRegularPolygon = function (parentElement, centerX, centerY, radius, sides, fillStyle, globalAlpha_Fill, lineWidth, strokeStyle, globalAlpha_Line)
 - drawRegularPolygon_Gradient_Linear = function (parentElement, centerX, centerY, radius, sides, gradientStops)
 - drawRegularPolygon_Rotation = function (parentElement, centerX, centerY, radius, sides, rotationAngle, fillStyle, globalAlpha_Fill, lineWidth, strokeStyle, globalAlpha_Line)

 - drawText = function (parentElement, x, y, textContent, fontSize, fontFamily, color, opacity)
 - drawText_Line = function (parentElement, x, y, textContent, fontSize, fontFamily, lineColor, opacity)
 - drawText_Line_Rotation = function (parentElement, x, y, textContent, fontSize, fontFamily, lineColor, opacity, rotationAngle)
 - drawText_Rotation = function (parentElement, x, y, textContent, fontSize, fontFamily, color, opacity, rotationAngle)

---