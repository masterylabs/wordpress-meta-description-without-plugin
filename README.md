# wordpress-meta-description-without-plugin
```
add_action('wp_head', function () {
    global $post;
    if (is_singular()) {
        $description = wp_strip_all_tags($post->post_content);
        $description = strip_shortcodes($description);
        $description = str_replace(["n", "r", "t"], ' ', $description);
        $description = mb_substr($description, 0, 160);
        echo '<meta name="description" content="' . esc_attr($description) . '">';
    }
    if (is_home()) {
        echo '<meta name="description" content="' . get_bloginfo('description') . '" />';
    }
    if (is_category()) {
        $description = wp_strip_all_tags(category_description());
        echo '<meta name="description" content="' . esc_attr($description) . '">';
    }
});
```

## SEO Checklist Plugin:
https://matts.tips/seo-checklist

## SEO Checklist Members:
https://masterylabs.com/my-products/seo-checklist-plugin
