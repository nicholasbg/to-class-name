import {trimAll} from "./trim-all";

/**
 * @description Get a string of classNames filtered and delimited by a space
 * @param {unknown[]} params Pass in classNames/collections of classNames.
 * @note
 * Each item in an array is unnested and treated the same as an individual
 * argument.
 * @note
 * Non-strings, empty strings, and whitespace-only strings are effectively
 * filtered-out.
 * @return {string} Unfiltered strings are joined, delimited by a space.
 * @example string(s) and variable(s)
 * var className;
 * var overlay = true;
 * toClassName('header', className, overlay && 'overlay');
 * @output "header overlay"
 * @example string(s) and array(s)
 * toClassName(
 *     'overlay',
 *     ['Uha5di_header', 'D87dza_facebook'],
 *     'social display'
 * );
 * @output "overlay Uha5di_header D87dda_facebook social display"
 */
export const toClassName = (...params) =>
  trimAll(
    /** @type {unknown[]} */ ([])
      .concat(...params)
      .map((param) => (typeof param === "string" ? param : ""))
      .join(" "),
  );
