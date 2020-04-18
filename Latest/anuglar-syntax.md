# Directives overview
There are three kinds of directives in Angular:

1) Components—directives with a template.
2) [Structural directives](https://angular.io/guide/structural-directives)—change the DOM layout by adding and removing DOM elements.
3) [Attribute directives](https://angular.io/guide/attribute-directives)—change the appearance or behavior of an element, component, or another directive.

* Components are the most common of the three directives. You saw a component for the first time in the Getting Started tutorial.

* Structural Directives change the structure of the view. Two examples are NgFor and NgIf. Learn about them in the Structural Directives guide.

```
<div *ngIf="hero" class="name">{{hero.name}}</div>



<div *ngFor="let hero of heroes; let i=index; let odd=odd; trackBy: trackById" [class.odd]="odd">
  ({{i}}) {{hero.name}}
</div>

<ng-template ngFor let-hero [ngForOf]="heroes" let-i="index" let-odd="odd" [ngForTrackBy]="trackById">
  <div [class.odd]="odd">({{i}}) {{hero.name}}</div>
</ng-template>


*ngFor="let item of [1,2,3]" 	<ng-template ngFor let-item [ngForOf]="[1,2,3]">
*ngFor="let item of [1,2,3] as items; trackBy: myTrack; index as i"	  <ng-template ngFor let-item [ngForOf]="[1,2,3]" let-items="ngForOf" [ngForTrackBy]="myTrack" let-i="index">
*ngIf="exp"	    <ng-template [ngIf]="exp">
*ngIf="exp as value"	<ng-template [ngIf]="exp" let-value="ngIf">




<div [ngSwitch]="hero?.emotion">
  <app-happy-hero    *ngSwitchCase="'happy'"    [hero]="hero"></app-happy-hero>
  <app-sad-hero      *ngSwitchCase="'sad'"      [hero]="hero"></app-sad-hero>
  <app-confused-hero *ngSwitchCase="'confused'" [hero]="hero"></app-confused-hero>
  <app-unknown-hero  *ngSwitchDefault           [hero]="hero"></app-unknown-hero>
</div>


<div>
  Pick your favorite hero
  (<label><input type="checkbox" checked (change)="showSad = !showSad">show sad</label>)
</div>
<select [(ngModel)]="hero">
  <ng-container *ngFor="let h of heroes">
    <ng-container *ngIf="showSad || h.emotion !== 'sad'">
      <option [ngValue]="h">{{h.name}} ({{h.emotion}})</option>
    </ng-container>
  </ng-container>
</select>

```

* Writing custom directives

```

Add this directive to the declarations array of the AppModule.

import { Directive, Input, TemplateRef, ViewContainerRef } from '@angular/core';

/**
 * Add the template content to the DOM unless the condition is true.
 */
@Directive({ selector: '[appUnless]'})
export class UnlessDirective {
  private hasView = false;

  constructor(
    private templateRef: TemplateRef<any>,
    private viewContainer: ViewContainerRef) { }

  @Input() set appUnless(condition: boolean) {
    if (!condition && !this.hasView) {
      this.viewContainer.createEmbeddedView(this.templateRef);
      this.hasView = true;
    } else if (condition && this.hasView) {
      this.viewContainer.clear();
      this.hasView = false;
    }
  }
}


<p *appUnless="condition" class="unless a">
  (A) This paragraph is displayed because the condition is false.
</p>

<p *appUnless="!condition" class="unless b">
  (B) Although the condition is true,
  this paragraph is displayed because appUnless is set to false.
</p>

```

* Attribute directives are used as attributes of elements. The built-in NgStyle directive in the Template Syntax guide, for example, can change

```
<p [appHighlight]="color" defaultColor="violet">
  Highlight me too!
</p>

ng generate directive highlight

import { Directive, ElementRef, HostListener, Input } from '@angular/core';

@Directive({
  selector: '[appHighlight]'
})
@Directive({
  selector: '[appHighlight]'
})
export class HighlightDirective {

  constructor(private el: ElementRef) { }

  @Input('appHighlight') highlightColor: string;
  
  @Input() defaultColor: string;

 
@HostListener('mouseenter') onMouseEnter() {
  this.highlight(this.highlightColor || this.defaultColor || 'red');
}
  @HostListener('mouseleave') onMouseLeave() {
    this.highlight(null);
  }

  private highlight(color: string) {
    this.el.nativeElement.style.backgroundColor = color;
  }
}




```
