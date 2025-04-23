MASKED_SECRET=$(echo "$SECRET_CONTENT" | tr '\n' '|' | sed 's/|/\\n/g')
    echo "::add-mask::$MASKED_SECRET"
